<script setup>

    const isFocused = ref(true);

    const props = defineProps({
        text: String,
        label: String,
        name: String
    })

    const emit = defineEmits(["update:modelValue"]);

    const boxChecked = defineModel('boxChecked')

</script>

<template>

    <div class="wrapper">
        <div class="wrapperBtn">
            <div class="button b2" id="button-13">
                <input @click="isFocused = !isFocused;" v-model="boxChecked" type="checkbox" class="checkbox" :name="props.name" />
                <div class="knobs">
                    <span></span>
                </div>
                <div class="layer"></div>
            </div>
        </div>
        <div :class="{ isActive: isFocused}" class="text">{{ props.text }}</div>
    </div>

</template>

<style scoped>

    * {
        user-select: none;
        -webkit-tap-highlight-color: transparent;
    }

    *:focus {
        outline: none;
    }

    .wrapper {
        display: flex;
        flex-direction: row !important;
        gap: 3vw;
        width: 90%;
        height: fit-content;
        justify-content: flex-start;
        padding: 10px;
    }

    .wrapperBtn {
        display: flex;
        align-items: center;
    }

    .text {
        color: var(---color-dark);
        font-size: 18px;
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 10px 15px;
        border: none;
        transition: 0.3s ease all;
        color: var(---color-red);
        text-decoration: line-through;
        text-wrap: wrap;
    }

    .text.isActive {
        text-decoration: none;
        color: var(---color-dark);
    }

    .knobs,
    .layer {
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
    }

    .button {
        position: relative;
        width: 74px;
        height: 36px;
        overflow: hidden;
    }

    .button.r,
    .button.r .layer {
        border-radius: 100px;
    }

    .button.b2 {
        border-radius: 2px;
    }

    .checkbox {
        position: relative;
        width: 100%;
        height: 100%;
        padding: 0;
        margin: 0;
        opacity: 0;
        cursor: pointer;
        z-index: 3;
    }

    .knobs {
        z-index: 2;
    }

    .layer {
        width: 100%;
        background-color: var(--color-white);
        transition: 0.3s ease all;
        z-index: 1;
    }

    #button-13 .knobs:before,
    #button-13 .knobs:after,
    #button-13 .knobs span {
        position: absolute;
        top: 4px;
        width: 20px;
        height: 10px;
        font-size: 10px;
        font-weight: bold;
        text-align: center;
        line-height: 1;
        padding: 9px 4px;
        border-radius: 2px;
        transition: 0.3s ease all;
    }

    #button-13 .knobs:before,
    #button-13 .knobs:after {
        color: var(--color-dark);
        z-index: 1;
    }

    #button-13 .knobs:before {
        content: "YES";
        left: 4px;
    }

    #button-13 .knobs:after {
        content: "NO";
        right: 4px;
    }

    #button-13 .knobs span {
        width: 25px;
        left: 37px;
        background-color: #1e5021;
        z-index: 2;
    }

    #button-13 .checkbox:checked+.knobs span {
        left: 4px;
        background-color: #8c1a1a;
    }

    #button-13 .checkbox:checked~.layer {
        background-color: var(--color-red);
    }

    @media only screen and (max-width: 540px) {
    .wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 80%;
        height: fit-content;
        padding: 10px;
    }

    .text {
        text-align: start;
    }

}
</style>