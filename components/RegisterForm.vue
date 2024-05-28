<script setup>

    import ButtonComp from './ButtonComp.vue';

    const nameField = ref(null);
    const emailField = ref(null);

    onMounted(() => {
        nameField.value = '';
        emailField.value = '';
    })

    function getInputValue(obj) {
        if (obj.fieldName === 'Name') {
            nameField.value = obj.text;
        } else if (obj.fieldName === 'Email') {
            emailField.value = obj.text;
        }
    }

</script>

<template>

    <form class="form-wrapper" name="signup" method="post" data-netlify="true" data-netlify-honeypot="bot-field">
        <div class="form">
            <InputText fieldName="Name"
                @update-input="getInputValue"
            />
            <InputText fieldName="Email"
                @update-input="getInputValue"/>
            <br>
            <CheckInput text="Do you want to subscribe to our newsletter?" v-model:box-checked="newsletterAgreement" name="newsletterAgreement"/>
            <CheckInput text="Would like to be a beta-tester for our application?" v-model:box-checked="betaTestingAgreement" name="betaTestingAgreement"/>
            <ButtonComp class="btn" text="Sign Up" altText="Thank you!" type="submit"/>
            <input type="hidden" name="form-name" value="signup" />
        </div>
    </form>



</template>

<style scoped>

    .form-wrapper {
        width: 100%;
        padding: 14px;
    }

    .form {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 100%;
    }

    .btn {
        align-self: center;
        margin-top: 30px;
    }

</style>