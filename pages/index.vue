<script setup>


</script>

<template>
    <div class="wrapper">
        <NavBar />
        <SectionComponent 
            :title="'COMMUTE?'"
            :body="'Day-to-Day Ride-sharing made easy.'"
            :color="'var(--color-dark)'"
            :textColor="'var(--color-white)'"
        >
            <RoadAnimation />
        </SectionComponent>
        <SectionComponent
            :title="'What is it?'"
            :color="'var(--color-light-green)'"
            :textColor="'var(--color-dark)'"
        >

        </SectionComponent>
    </div>
</template> 

<style scoped>

    .wrapper {
        width: 100%;
    }

</style>