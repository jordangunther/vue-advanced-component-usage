<template>
    <div>
        <span class="title">
            <slot name="red-title"></slot>
        </span>
<!--        Just slot will pull in any elements inside of slot that are unnamed-->
        <slot></slot>
    </div>
</template>

<script>

</script>

<style scoped>
    div {
        border: 1px solid red;
        background-color: lightcoral;
        padding: 30px;
        margin: 20px auto;
        text-align: center
    }
</style>