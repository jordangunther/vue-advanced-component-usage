<template>
    <div>
        <span class="title">
            <slot name="blue-title"></slot>
            <slot name="blue-subtitle"></slot>
        </span>
    </div>
</template>

<script>

</script>

<style scoped>
    div {
        border: 1px solid blue;
        background-color: lightblue;
        padding: 30px;
        margin: 20px auto;
        text-align: center
    }
</style>