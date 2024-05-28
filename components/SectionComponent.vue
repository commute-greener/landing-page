<script setup>

    const props = defineProps({
        title: String,
        body: String,
        color: String,
        textColor: String,
    })

</script>

<template>

    <div class="section-container">
        <div class="title-container">
            <h1 class="section-title">{{ props.title }}</h1>
            <div v-if="props.body" class="section-body">{{ props.body }}</div>
        </div>

        <slot class="slot-space"></slot>
    </div>

</template>

<style scoped>

    .section-container {
        height: fit-content;
        width: 100%;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        gap: 3svh;
        padding-top: 24px;
        background-color: v-bind('props.color');
        overflow: hidden;
        color: v-bind('props.textColor');
    }

    .title-container {
        width: 100%;
        height: fit-content;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .section-title {
        font-weight: bold;
        margin-top: 5svh;
        text-align: center;
    }

    .section-body {
        font-size: 18px;
        text-align: center;
    }

</style>