<script>
    export default {
        name: 'myInput',
        props: {
            modelValue: [String, Number]
        },
        methods: {
            updateInput(event) {
                this.$emit('update:modelValue', event.target.value);
            }
        }
    }
</script>

<template>
    <input :value="modelValue" @input="updateInput" type="text" class="input">
</template>

<style>
    .input {
        margin: 0;
        padding: 0;
        border: 0;
        outline: none;

        padding: 10px;
        border-radius: 10px;
        background-color: rgb(241,255,207);

        font-size: 16px;
        line-height: 1.2;
        font-weight: 400;
    }
</style>