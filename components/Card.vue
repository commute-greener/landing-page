<script setup>

defineProps({
  text: String,
  iconName: String,
})

</script>

<template>

  <div class="card">
    <Icon class="card-icon" :name="iconName" size="48"/>
    <p class="card-text">{{ text }}</p>
  </div>

</template>

<style scoped>

    .card {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 70vw;
        max-width: 250px;
        height: 230px;
        margin-top: -8dvh;
        padding: 8px 24px;
        border: 1px solid var(--color-dark);
        border-radius: 10px;
        gap: 16px;
        background-color: rgba(27, 27, 27, 0.15);
    }

    .card-text {
        text-align: justify;
    }

</style>