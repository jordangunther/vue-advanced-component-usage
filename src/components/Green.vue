<template>
    <div :class="greenClass">
        <span class="title">
            <slot name="green-title"></slot>
        </span>
<!--        adding text inside of a slot will serve as a default if the name doesn't exist-->
        <slot name="green-subtitle">Sometimes I am cool</slot>
        <hr>
        <button @click="darker()">make me darker</button>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                greenClass: 'blue'
            }
        },
        methods: {
            darker() {
                this.greenClass = 'darker'
            }
        }
    }
</script>

<style scoped>
    div {
        border: 1px solid green;
        background-color: lightgreen;
        padding: 30px;
        margin: 20px auto;
        text-align: center
    }

    /*This style overrides the style in App.vue*/
    .title {
        color: darkgreen;
    }
    .darker {
        background-color: green;
    }
    .darker .title {
        color: greenyellow;
    }
</style>