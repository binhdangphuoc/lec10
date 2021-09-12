<template>
  <div class="success">
      <h1>Success!</h1>
      <button @click="buyOk()">OK</button>
  </div>
</template>

<script>
export default {
    name: 'SummarySuccess',
    methods: {
      buyOk() {
        this.$emit('buyOk')
      }
    }
}
</script>

<style>
  h1{
    color: red;
  }
  .success {
    background-color: greenyellow;
    width: 200px;
    height: 100px;
    margin: auto;
    text-align: center;
  }
</style>