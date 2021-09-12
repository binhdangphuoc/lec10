<template>
  <div class="summary">
      <div>
          <img src="../../../../public/order-summary.png">
      </div>
      <div class="infor">
          <h3>Order Summary</h3>
          <p>You can now listen to million of songs, audiobooks, and postcasts
              on any device anywhere you like!
          </p>
      </div>
  </div>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style scoped>
    .summary img{
        width: 100%;
        overflow: hidden;
        border-top-left-radius: 50px;
        border-top-right-radius: 50px;
    }
    .infor {
        text-align: center;
        padding: 0 40px;
    }
    .infor h3{
        font-size: 1.8rem;
        margin: 20px 0px;
        color: rgb(31,49,82);
        font-weight: 900;
    }
    .infor p {
        font-size: 1rem;
        color: rgb(130,140,165);
        font-weight: 500;
        line-height: 1.4rem;
    }
</style>