<script setup>

</script>

<template>

    <div class="phone-container">
        <div class="explanations">
            <div class="explanation-item">
                <div class="explanation-num">1</div>
                <div class="explanation-text">Only one app for driver and passenger</div>
            </div>
            <div class="explanation-item">
                <div class="explanation-num">2</div>
                <div class="explanation-text">Easy setup for your everyday trip</div>
            </div>
            <div class="explanation-item">
                <div class="explanation-num">3</div>
                <div class="explanation-text">Community based ratings for safer rides</div>
            </div>
            <div class="explanation-item">
                <div class="explanation-num">4</div>
                <div class="explanation-text">Never be late with realtime ETAs</div>
            </div>
        </div>
        <img src="/phone-framed-app.png" alt="Image of the app in a phone">
    </div>

</template>

<style scoped>

    .phone-container {
        width: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: end;
    }

    .explanations {
        display: flex;
        flex-direction: column;
        gap: 5px;
    }

    .explanation-item {
        font-size: 18px;
        display: flex;
        flex-direction: row;
        padding-left: 24px;
        gap: 20px;
        align-items: center;
    }

    .explanation-num {
        border: 2px solid var(--color-light-green);
        border-radius: 50%;
        width: 28px;
        height: 28px;
        font-weight: bolder;
        text-align: center;
        line-height: 28px;
        color: var(--color-light-green);
    }

    img {
        align-self: center;
        height: 40svh;
        width: 70%;
        max-width: 250px;
        object-fit: cover; 
        object-position: 100% 0;
    }

</style>