<template>
    <div>
        <div id="on" @click="switched(true)" :class="{active:isOnValue}"> On

        </div>
        <div id="off" @click="switched(false)" :class="{active:!isOnValue}"> Off

        </div>
    </div>
</template>

<script>
    export default {
        props:{
            isOnValue:Boolean,
        },
        methods:{
            switched(isOn){
                this.$emit('switched-event', isOn);
            }
        }
    }
</script>

<style scoped>
    #on, #off{
        width: 40px;
        height: 20px;
        background-color: lightgray;
        padding: 2px;
        display: inline-block;
        margin: 10px -2px;
        box-sizing: content-box;
        cursor: pointer;
        text-align: center;
    }
    #on:hover, #on.active{
        background-color: lightgreen;
    }
    #off:hover, #off.active{
        background-color: lightcoral;
    }
</style>