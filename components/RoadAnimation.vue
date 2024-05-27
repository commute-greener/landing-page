<script setup>

    let arrayOfInnerLane = reactive([])

    const roadParams = {
        road: {
            height: '50px',
        },
        outerLanes: {
            height: '3px',
        },
        innerLane: {
            height: '5px',
            length: '25px',
            gap: '15px',
        },
        car: {
            height: '36px',
            length: '70px',
            radiusBack: '5px',
            radiusFront: '20px',
            light: {
                height: '30px',
                length: '40px',
                color: 'rgba(251, 255, 5, 0.4)',
            }
        }
    }

    function returnNumFromStr(str) {
        return +str.slice(0, -2);
    }

    onMounted(() => {
        arrayOfInnerLane.slice(arrayOfInnerLane.length)
        let numOfCentralMarkings = Math.floor((window.innerWidth ) / (returnNumFromStr(roadParams.innerLane.gap) + returnNumFromStr(roadParams.innerLane.length)));
        for (let i = 0; i <= numOfCentralMarkings; i++) {
            arrayOfInnerLane.push(i)
        }

        window.onresize = () => {
            arrayOfInnerLane.slice(arrayOfInnerLane.length)
            let numOfCentralMarkings = Math.floor((window.innerWidth ) / (returnNumFromStr(roadParams.innerLane.gap) + returnNumFromStr(roadParams.innerLane.length)));
            for (let i = 0; i <= numOfCentralMarkings; i++) {
                arrayOfInnerLane.push(i)
            }
        }
    })

    onBeforeUnmount(() => {
        window.onresize = null;
    })

</script>

<template>
    <div class="road">
        <div class="outside-lane"></div>
        <div class="car">
            <div class="light light-top"></div>
            <div class="light light-bot"></div>
        </div>
        <div class="middlane-container">
            <div class="inner-lane" v-for="items in arrayOfInnerLane"></div>
        </div>
        <div class="outside-lane"></div>
    </div>
</template>

<style scoped> 
    .road {
        margin-top: 10px;
        height: v-bind('roadParams.road.height');
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        transform: rotate(2deg);
    }

    .middlane-container {
        height: fit-content;
        width: 100%;
        display: flex;
        gap: v-bind('roadParams.innerLane.gap');
    }

    .outside-lane, .inner-lane, .car {
        background-color: var(--color-white);
    }

    .outside-lane {
        height: v-bind('roadParams.outerLanes.height');
        width: 100%;
    }

    .inner-lane {
        height: v-bind('roadParams.innerLane.height');
        width: v-bind('roadParams.innerLane.length');
    }

    .car {
        position: absolute;
        top: calc((v-bind('roadParams.road.height') - v-bind('roadParams.car.height')) / 2);
        border-radius: v-bind('roadParams.car.radiusBack') v-bind('roadParams.car.radiusFront') v-bind('roadParams.car.radiusFront') v-bind('roadParams.car.radiusBack');
        height: v-bind('roadParams.car.height');
        width: v-bind('roadParams.car.length');
        animation: 10s linear 1s infinite running cross;
        transform: translateX(-150%);
    }

    .car::after {
        content: '';
        height: calc(v-bind('roadParams.car.height') * 0.85);
        width: v-bind('roadParams.car.light.length');
        background-color: var(--color-dark);
        clip-path: polygon(50% 0, 100% 10%, 100% 90%, 50% 100%);
        position: absolute;
        right: calc(v-bind('roadParams.car.length') / 4.5);
        top: 50%;
        transform: translateY(-50%);
        z-index: 2;
    }

    .light {
        position: absolute;
        width: v-bind('roadParams.car.light.length');
        height: v-bind('roadParams.car.light.height');
        background-color: v-bind('roadParams.car.light.color');
        clip-path: polygon(100% 0, 0 50%, 100% 100%);
    }

    .light-top {
        right: calc(-1 * v-bind('roadParams.car.light.length') * 0.88);
        top: calc(-1 * v-bind('roadParams.car.light.height') * 0.22);
    }

    .light-bot {
        right: calc(-1 * v-bind('roadParams.car.light.length') * 0.88);
        bottom: calc(-1 * v-bind('roadParams.car.light.height') * 0.22);
    }

    @keyframes cross {
        50% {transform: translateX(calc(130vw + 2 * v-bind('roadParams.car.length')));}
        100% {transform: translateX(calc(130vw + 2 * v-bind('roadParams.car.length')));}
    }

</style>