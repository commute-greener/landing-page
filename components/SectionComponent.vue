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

        <slot></slot>
    </div>

</template>

<style scoped>

    .section-container {
        height: 100dvh;
        width: 100%;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        gap: 5svh;
        padding-top: 24px;
        background-color: v-bind('props.color');
        overflow: hidden;
    }

    .title-container {
        width: 100%;
        height: fit-content;
        display: flex;
        flex-direction: column;
        align-items: center;
        color: v-bind('props.textColor');
    }

    .section-title {
        font-weight: bold;
        margin-top: 5svh;
    }

    .section-body {
        font-size: 18px;
        text-align: center;
    }

</style>