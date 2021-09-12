<template>
  <div id="app">
    <OrderSummary
      v-if= "show == 0"
      @buy = 'show = 1'
      @cancel = 'show = 2'
    />
    <SummarySuccess
      v-if="show==1"
      @buyOk = 'show = 0'
    />
    <CancelOrder
      v-if="show == 2"
      @cancelOk = 'show = 0'
    />
  </div>
    
  
</template>

<script>
import OrderSummary from './components/order_summary/OrderSummary.vue'
import SummarySuccess from './components/order_summary/SummarySuccess.vue'
import CancelOrder from './components/order_summary/CancelOrder.vue'

export default {
  name: 'App',
  components: {OrderSummary, SummarySuccess, CancelOrder},
  data() {
    return {
      show: 0,
    }
  }
}
</script>

<style>
  
</style>
