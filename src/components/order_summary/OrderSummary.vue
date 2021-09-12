<template>
   <div class="ordersummary">
      <Header/>
      <SelectPlan/>
      <div class="btn">
         <div class="submit" @click="buy()">Process to Payment</div>
         <div class="cancel" @click="cancel()">Cancel Order</div>
      </div>
   </div>
  
</template>

<script>
 import Header  from "./header/Header.vue";
 import SelectPlan  from "./selectPlan/SelectPlan.vue";
export default {
   name: 'OrderSummary',
   components: {
      Header, SelectPlan,
   },
   methods: {
      buy() {
         this.$emit('buy')
      },
      cancel() {
         this.$emit('cancel')
      }
   }
}
</script>

<style scoped>
   @media only screen and (min-width: 500px) {
      .ordersummary {
         width: 500px;
         margin: auto;
      }  
   }

   .btn {
        display: block;
        text-align: center;
        margin: 20px auto;
    }
    .btn .submit {
        background-color: rgb(69,108,225);
        height: 40px;
        line-height: 40px;
        border-radius: 10px;
        margin: 0 auto;
        font-size: 1.1rem;
        color: white;
        margin: 10px 30px;
        cursor: pointer;
        transition: all .5s ease-in-out;
         font-weight: bold;
    }
    .btn .submit:hover {
        transform: scale(1.1);
    }
    .btn .cancel {
        background-color: rgb(183,188,206);
        height: 40px;
        line-height: 40px;
        border-radius: 10px;
        margin: 0 auto !important;
        font-size: 1.1rem;
        color: white;
        margin: 0px 30px;
        cursor: pointer;
        transition: all .5s ease-in-out;
        font-weight: bold;
    }
    .btn .cancel:hover {
        background-color: rgb(130,140,165);
        transform: scale(1.1);
    }

</style>