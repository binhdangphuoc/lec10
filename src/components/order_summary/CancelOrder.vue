<template>
    <div class="cancel">
        <h1>Canceled</h1>
        <button @click="cancelOk()">OK</button>
    </div>
  
</template>

<script>
export default {
    name: 'CancelOrder',
    methods: {
        cancelOk() {
            console.log("cancelOk")
            this.$emit('cancelOk')
        }
    }
}
</script>

<style>
    h1{
        color: gray;
    }
    .cancel {
        width: 200px;
        height: 100px;
        background-color: greenyellow;
        margin: auto;
        text-align: center;
    }
</style>