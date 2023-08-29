<script>
    export default {
        name: 'myButton'
    }
</script>

<template>
    <button type="button" class="button">
        <slot></slot>
    </button>
</template>

<style>
    .button {
        margin: 0;
        padding: 0;
        border: 0;
        outline: none;

        font-size: 16px;
        line-height: 1.2;
        font-weight: 700;

        padding: 10px;
        border-radius: 10px;
        background-color: rgb(241,255,207);
        transition: all ease-in 0.7s;
    }

    .button:hover {
        transform: translateY(-2px);
        opacity: .7;
        cursor: pointer;
    }
</style>