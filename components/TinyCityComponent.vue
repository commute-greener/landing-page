<script setup>

    let windowWidth = ref(undefined)

    onMounted(() => {
        windowWidth.value = `${window.innerWidth}px`;

        window.onresize(() => {
            windowWidth.value = `${window.innerWidth}px`;
        })
    })

    onBeforeUnmount(() => {
        window.onresize = null;
    })

</script>

<template>
        <div class="city-container">
            <div class='highscraper'>
                <div class='wall-one'>
                    <div></div>
                </div>
                <div class='wall-two'>
                    <div></div>
                </div>
                <div class='roof'>
                    <div>
                        <div></div>
                        <div></div>
                    </div>
                    <div>
                        <div></div>
                        <div></div>
                    </div>
                    <div></div>
                </div>
            </div>

            <div class='brickhouse'>
                <div class='wall-one'>
                    <div></div>
                </div>
                <div class='wall-two'>
                    <div></div>
                </div>
                <div class='roof'>
                    <div>
                        <div></div>
                        <div></div>
                    </div>
                    <div>
                        <div></div>
                        <div></div>
                    </div>
                </div>
            </div>

            <div class='leaves'>
                <div></div>
            </div>
            <div class='wood'></div>

            <div class='ground-cropped'>
                <div class='shadow-brickhouse'></div>
                <div class='shadow-highscraper'></div>

                <div class='car-one red'></div>
                <div class='car-one blue'></div>
                <div class='car-two black'></div>

            </div>

            <div class='water'></div>
            <div class='fontain'>
                <div></div>
            </div>
            <div class='water-drops'>
                <div></div>
                <div></div>
                <div></div>
                <div></div>
            </div>

            <div class='road'></div>
            <div class='ground'>
                <div></div>
                <div></div>
                <div></div>
                <div></div>
            </div>
        </div>
</template>

<style scoped>

    .city-container {
        position: relative;
        width: v-bind('windowWidth');
        height: 300px;
        align-self: center;
        transform: translate(25%, 5%);
        margin-top: 10dvh;
    }

    .ground {
        position: absolute;
        display: block;
        background-color: #cac4ae;
        width: 200px;
        height: 200px;
        transform: rotateZ(45deg);
        z-index: 1;
    }

    .ground div:first-child {
        position: absolute;
        display: block;
        background-color: #83a75f;
        width: 70px;
        height: 90px;
        bottom: 0px;
        right: 0px;
        z-index: 2;
    }

    .ground div:nth-child(2) {
        position: absolute;
        display: block;
        background-color: transparent;
        width: 60px;
        height: 50px;
        top: 0px;
        right: 0px;
        z-index: 3;
    }

    .ground div:nth-child(3) {
        position: absolute;
        display: block;
        background-color: #b2ab93;
        width: 10px;
        height: 200px;
        top: 5px;
        right: -10px;
        z-index: 4;
        transform: skewY(45deg);
    }

    .ground div:nth-child(4) {
        position: absolute;
        display: block;
        background-color: #d5cfba;
        width: 200px;
        height: 10px;
        top: 200px;
        right: -5px;
        z-index: 5;
        transform: skewX(45deg);
    }

    .road {
        position: absolute;
        display: block;
        background-color: #989899;
        width: 40px;
        height: 200px;
        transform: rotateZ(45deg);
        top: 0px;
        left: 80px;
        z-index: 2;
    }

    .road:after {
        position: absolute;
        display: block;
        content: '';
        background-color: #989899;
        width: 30px;
        height: 200px;
        transform: rotateZ(90deg);
        top: -15px;
        left: 5px;
        z-index: 2;
    }

    /***************************************************************/
    /*********************** highscraper ***************************/
    /***************************************************************/

    .highscraper {
        position: absolute;
        display: block;
        background-color: transparent;
        width: 60px;
        height: 80px;
        transform: rotateZ(45deg);
        top: 53px;
        left: -10px;
        z-index: 999;
    }

    .highscraper .wall-one {
        position: absolute;
        display: block;
        background-color: #7da1bf;
        width: 60px;
        height: 150px;
        transform: skewX(45deg);
        top: -70px;
        left: -75px;
    }

    .highscraper .wall-one div {
        position: absolute;
        display: block;
        background-color: black;
        opacity: 0.2;
        width: 60px;
        height: 2px;
        top: 10px;
        left: 0px;

        box-shadow: 0 -8px 0 0 black,
            0 10px 0 0 black,
            0 20px 0 0 black,
            0 30px 0 0 black,
            0 40px 0 0 black,
            0 50px 0 0 black,
            0 60px 0 0 black,
            0 70px 0 0 black,
            0 80px 0 0 black,
            0 90px 0 0 black,
            0 100px 0 0 black,
            0 110px 0 0 black,
            0 120px 0 0 black,
            0 130px 0 0 black;
    }

    .highscraper .wall-two {
        position: absolute;
        display: block;
        background-color: #6389a8;
        width: 150px;
        height: 80px;
        transform: skewY(45deg);
        top: -75px;
        left: -90px;
    }

    .highscraper .wall-two div {
        position: absolute;
        display: block;
        background-color: black;
        opacity: 0.2;
        width: 2px;
        height: 80px;
        top: 0px;
        left: 10px;

        box-shadow: -8px 0 0 0 black,
            10px 0 0 0 black,
            20px 0 0 0 black,
            30px 0 0 0 black,
            40px 0 0 0 black,
            50px 0 0 0 black,
            60px 0 0 0 black,
            70px 0 0 0 black,
            80px 0 0 0 black,
            90px 0 0 0 black,
            100px 0 0 0 black,
            110px 0 0 0 black,
            120px 0 0 0 black,
            130px 0 0 0 black;
    }

    .highscraper .roof {
        position: absolute;
        display: block;
        background-color: #444;
        width: 60px;
        height: 80px;
        top: -150px;
        left: -150px;

        box-shadow: inset 0 0 0 4px #313131;
    }

    /*---------------- one -----------------------------*/
    .highscraper .roof>div:nth-child(1) {
        position: absolute;
        display: block;
        background-color: #494949;
        width: 10px;
        height: 10px;
        top: 50px;
        left: 35px;
    }

    .highscraper .roof>div:nth-child(1) div:nth-child(1) {
        position: absolute;
        display: block;
        background-color: #323232;
        width: 2px;
        height: 10px;
        top: 1px;
        left: 10px;
        transform: skewY(45deg);
    }

    .highscraper .roof>div:nth-child(1) div:nth-child(2) {
        position: absolute;
        display: block;
        background-color: #555;
        width: 10px;
        height: 2px;
        top: 10px;
        left: 1px;
        transform: skewX(45deg);
    }

    /*------------------- two --------------------------*/
    .highscraper .roof>div:nth-child(2) {
        position: absolute;
        display: block;
        background-color: #494949;
        width: 15px;
        height: 15px;
        top: 20px;
        left: 20px;
    }

    .highscraper .roof>div:nth-child(2) div:nth-child(1) {
        position: absolute;
        display: block;
        background-color: #323232;
        width: 5px;
        height: 15px;
        top: 3px;
        left: 15px;
        transform: skewY(45deg);
    }

    .highscraper .roof>div:nth-child(2) div:nth-child(2) {
        position: absolute;
        display: block;
        background-color: #555;
        width: 15px;
        height: 5px;
        top: 15px;
        left: 3px;
        transform: skewX(45deg);
    }

    /*------------------- three tall and thin --------------------------*/
    .highscraper .roof>div:nth-child(3) {
        position: absolute;
        display: block;
        background-color: #333;
        width: 70px;
        height: 2px;
        top: 30px;
        left: -40px;
        transform: rotateZ(45deg);
        box-shadow: -7px -7px 0 0 #333;
    }

    /***************************************************************/
    /*********************** warehouse *****************************/
    /***************************************************************/

    .brickhouse {
        position: absolute;
        display: block;
        background-color: transparent;
        width: 50px;
        height: 50px;
        transform: rotateZ(45deg);
        top: -25px;
        left: 72px;
        z-index: 6;
    }

    .brickhouse .wall-one {
        position: absolute;
        display: block;
        background-color: #cb7a4d;
        width: 50px;
        height: 50px;
        transform: skewX(45deg);
        top: 0px;
        left: -25px;
    }

    .brickhouse .wall-one div {
        position: absolute;
        display: block;
        background-color: black;
        opacity: 0.35;
        width: 5px;
        height: 7px;
        top: 3px;
        left: 8px;

        box-shadow: 0 10px 0 0 black,
            0 20px 0 0 black,
            0 30px 0 0 black,
            0 40px 0 0 black,
            10px 0px 0 0 black,
            10px 10px 0 0 black,
            10px 20px 0 0 black,
            10px 30px 0 0 black,
            10px 40px 0 0 black,
            20px 0px 0 0 black,
            20px 10px 0 0 black,
            20px 20px 0 0 black,
            20px 30px 0 0 black,
            20px 40px 0 0 black,
            30px 0px 0 0 black,
            30px 10px 0 0 black,
            30px 20px 0 0 black,
            30px 30px 0 0 black,
            30px 40px 0 0 black;
    }

    .brickhouse .wall-two {
        position: absolute;
        display: block;
        background-color: #b76538;
        width: 50px;
        height: 50px;
        transform: skewY(45deg);
        top: -25px;
        left: 0px;
    }

    .brickhouse .wall-two div {
        position: absolute;
        display: block;
        background-color: black;
        opacity: 0.35;
        width: 7px;
        height: 5px;
        top: 8px;
        left: 3px;

        box-shadow: 10px 0 0 0 black,
            20px 0 0 0 black,
            30px 0 0 0 black,
            40px 0 0 0 black,
            0px 10px 0 0 black,
            10px 10px 0 0 black,
            20px 10px 0 0 black,
            30px 10px 0 0 black,
            40px 10px 0 0 black,
            0px 20px 0 0 black,
            10px 20px 0 0 black,
            20px 20px 0 0 black,
            30px 20px 0 0 black,
            40px 20px 0 0 black,
            0px 30px 0 0 black,
            10px 30px 0 0 black,
            20px 30px 0 0 black,
            30px 30px 0 0 black,
            40px 30px 0 0 black;
    }

    .brickhouse .roof {
        position: absolute;
        display: block;
        background-color: #444;
        width: 50px;
        height: 50px;
        top: -50px;
        left: -50px;

        box-shadow: inset 0 0 0 3px #313131;
    }

    /*---------------- one -----------------------------*/
    .brickhouse .roof>div:nth-child(1) {
        position: absolute;
        display: block;
        background-color: #494949;
        width: 20px;
        height: 10px;
        top: 5px;
        left: 10px;
    }

    .brickhouse .roof>div:nth-child(1) div:nth-child(1) {
        position: absolute;
        display: block;
        background-color: #323232;
        width: 2px;
        height: 10px;
        top: 1px;
        left: 20px;
        transform: skewY(45deg);
    }

    .brickhouse .roof>div:nth-child(1) div:nth-child(2) {
        position: absolute;
        display: block;
        background-color: #555;
        width: 20px;
        height: 2px;
        top: 10px;
        left: 1px;
        transform: skewX(45deg);
    }

    /*------------------- two --------------------------*/
    .brickhouse .roof>div:nth-child(2) {
        position: absolute;
        display: block;
        background-color: #494949;
        width: 15px;
        height: 15px;
        top: 20px;
        left: 20px;
    }

    .brickhouse .roof>div:nth-child(2) div:nth-child(1) {
        position: absolute;
        display: block;
        background-color: #323232;
        width: 5px;
        height: 15px;
        top: 3px;
        left: 15px;
        transform: skewY(45deg);
    }

    .brickhouse .roof>div:nth-child(2) div:nth-child(2) {
        position: absolute;
        display: block;
        background-color: #555;
        width: 15px;
        height: 5px;
        top: 15px;
        left: 3px;
        transform: skewX(45deg);
    }

    /************************************************************/
    /************************************************************/
    /************************************************************/

    .ground-cropped {
        position: absolute;
        display: block;
        background-color: transparent;
        width: 200px;
        height: 200px;
        transform: rotateZ(45deg);
        z-index: 3;
        overflow: hidden;
    }

    .shadow-brickhouse {
        position: absolute;
        display: block;
        background-color: rgba(0, 0, 0, 0.2);
        width: 200px;
        height: 50px;
        z-index: 3;
        transform: rotateZ(-45deg);
        top: -57px;
        left: 5px;
    }

    .shadow-highscraper {
        position: absolute;
        display: block;
        background-color: rgba(0, 0, 0, 0.2);
        width: 250px;
        height: 90px;
        z-index: 3;
        transform: rotateZ(-45deg);
        top: 26px;
        left: 0px;
    }



    .leaves {
        position: absolute;
        display: block;
        background-color: #48773c;
        width: 75px;
        height: 60px;
        border-radius: 10px;
        z-index: 999;
        transform: rotateZ(-45deg);
        top: 120px;
        left: 66px;
        overflow: hidden;

        box-shadow: -1px 1px 0 0 #3c6a30,
            -2px 2px 0 0 #3c6a30,
            -3px 3px 0 0 #3c6a30,
            -4px 4px 0 0 #3c6a30,
            -5px 5px 0 0 #3c6a30,
            -6px 6px 0 0 #3c6a30,
            -7px 7px 0 0 #3c6a30,
            -8px 8px 0 0 #3c6a30,
            -9px 9px 0 0 #3c6a30,
            -10px 10px 0 0 #3c6a30;
    }

    .leaves div {
        position: absolute;
        display: block;
        background-color: rgba(0, 0, 0, 0.15);
        width: 100px;
        height: 100px;
        z-index: 3;
        transform: rotateZ(-45deg);
        top: -72px;
        left: 50px;
    }

    .wood {
        position: absolute;
        display: block;
        background-color: #462512;
        content: '';
        width: 4px;
        height: 25px;
        z-index: 998;
        border-radius: 2px;
        top: 174px;
        left: 76px;

        box-shadow: -10px -10px 0 0 #462512,
            10px 10px 0 0 #462512,
            20px 20px 0 0 #462512,
            30px 10px 0 0 #462512,
            40px 0px 0 0 #462512,
            50px -10px 0 0 #462512,
            60px -20px 0 0 #462512;
    }

    .water {
        position: absolute;
        display: block;
        background-color: #6389a8;
        width: 30px;
        height: 40px;
        z-index: 3;
        transform: rotateZ(-45deg);
        top: 75px;
        left: 173px;
        box-shadow: 0 0 0 4px rgba(0, 0, 0, 0.15);
    }

    .water-drops div:nth-child(1) {
        position: absolute;
        display: block;
        background-color: #92b5d2;
        width: 4px;
        height: 0px;
        border-radius: 4px;
        bottom: -90px;
        left: 180px;
        z-index: 999;
        opacity: 0.4;
        animation: water-drops 2s ease infinite;
        animation-delay: .25s;
    }

    .water-drops div:nth-child(2) {
        position: absolute;
        display: block;
        background-color: #92b5d2;
        width: 4px;
        height: 0px;
        border-radius: 4px;
        bottom: -95px;
        left: 185px;
        z-index: 999;
        opacity: 0.4;
        animation: water-drops 2s ease infinite;
        animation-delay: .5s;
    }

    .water-drops div:nth-child(3) {
        position: absolute;
        display: block;
        background-color: #92b5d2;
        width: 4px;
        height: 0px;
        border-radius: 4px;
        bottom: -100px;
        left: 190px;
        z-index: 999;
        opacity: 0.4;
        animation: water-drops 2s ease infinite;
        animation-delay: .75s;
    }

    .water-drops div:nth-child(4) {
        position: absolute;
        display: block;
        background-color: #92b5d2;
        width: 4px;
        height: 0px;
        border-radius: 4px;
        bottom: -105px;
        left: 195px;
        z-index: 999;
        opacity: 0.4;
        animation: water-drops 2s ease infinite;
        animation-delay: 1s;
    }

    @keyframes water-drops {
        0% {
            height: 0px;
            border-radius: 3px;
        }

        50% {
            height: 25px;
        }

        100% {
            height: 0px;
        }
    }

    .car-one {
        position: absolute;
        display: block;
        width: 15px;
        height: 7px;
        top: 86px;
        left: 200px;
        box-shadow: 2px 2px 0 0 #333;
        z-index: -998;
    }

    .car-one.red {
        background-color: #c52735;
        animation: red-car 9s linear infinite;
    }

    @keyframes red-car {
        0% {
            top: 73px;
            left: 420px;
        }

        100% {
            top: 73px;
            left: -180px;
        }
    }

    .car-one.blue {
        background-color: #2d6398;
        animation: blue-car 9s linear infinite;
    }

    @keyframes blue-car {
        0% {
            top: 86px;
            left: -180px;
        }

        100% {
            top: 86px;
            left: 420px;
        }
    }

    .car-two {
        position: absolute;
        display: block;
        width: 7px;
        height: 15px;
        top: -100px;
        left: 85px;
        box-shadow: 2px 2px 0 0 #333;
        z-index: -998;
    }

    .car-two.black {
        background-color: #7d7d7d;
        animation: black-car 9s ease infinite;
    }

    @keyframes black-car {
        0% {
            top: -50px;
            left: 85px;
        }

        35% {
            top: 37px;
            left: 85px;
        }

        62% {
            top: 37px;
            left: 85px;
        }

        65% {
            top: 34px;
            left: 85px;
        }

        100% {
            top: 280px;
            left: 85px;
        }
    }

</style>