<script setup>

    const wrapper = ref(null);
    const screenSize = ref(undefined);

    onMounted(() => {
        screenSize.value = getComputedStyle(wrapper.value, '::after').content.replace(/\"/g, '');
        console.log(screenSize.value === "s")

        window.onresize = () => {
            screenSize.value = getComputedStyle(wrapper.value, '::after').content.replace(/\"/g, '');
        }
    })

    onBeforeUnmount(() => {
        window.onresize = null;
    })

</script>

<template>
    <div ref="wrapper" class="wrapper">
        <NavBar />
        <SectionComponent 
            :title="'COMMUTE'"
            :body="'Day-to-Day Ride-sharing made easy.'"
            :color="'var(--color-dark)'"
            :textColor="'var(--color-white)'"
        >
            <RoadAnimation />
            <PhoneElementComponent />
        </SectionComponent>
        <SectionComponent
            :title="'What is it?'"
            :color="'var(--color-light-green)'"
            :textColor="'var(--color-dark)'"
        >
            <div class="city-wrapper">
                <TinyCityComponent />
            </div>
        </SectionComponent>
    </div>
</template> 

<style scoped>

    .wrapper {
        width: 100%;
    }

    .wrapper::after {
        content: 'l';
        display: none;
        visibility: hidden;
    }

    @media only screen and (max-width: 768px) {
        .wrapper::after {
            content: 's';
        }
    }

</style>