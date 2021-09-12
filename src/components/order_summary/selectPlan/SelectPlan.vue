<template>
<div class="order">
  <div class="content">
      <ul>
          <li class="icon-music"><i class="fas fa-music"></i></li>
          <li class="selected" v-show="!change">
              <span class="plan">{{selected}}</span><br>
              <span class="price">{{price | formatPrice}}</span>
            </li>

            <li class="selected" v-if="change">
                <div class="showSelect" @click="change=false">
                    <span class="manual" @click="selected='Manual'">Manual</span><br>
                    <span class="pro" @click="selected='Pro'">Pro</span><br>
                    <span class="premium" @click="selected='Premium'">Premium</span>
                </div>   
          </li>
          
          <li class="btn-change" @click="change=!change">
              change
          </li>
      </ul>
    </div>
</div>
</template>

<script>
export default {
    name: 'SelectPlan',
    data() {
        return {
            selected: "Manual",
            price: 59.99,
            change: false,
        }
    },
    filters: {
        formatPrice: function(price){
            return "$" + price + "/year"
        }
    },
    methods: {
         submit(){
             console.log("submit")
            // if(this.change=true) return
            // else this.$emit('submit_order')
        },
        cancel(){
             console.log("cancel")
            // this.$emit('cancel')
        }
    },
    watch: {
        selected: function(newVal) {
            this.change = false;
            switch(newVal){
                case 'Manual': this.price = 59.99;
                    break;
                case 'Pro': this.price = 99.99;
                    break;
                case 'Premium': this.price = 199.99;
                    break;
                default: this.price = 59.99;
                    break;
            }
        }
    }
}
</script>

<style>

    .content ul {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin: 0px 15px;
        padding: 10px 15px;
        font-size: 1rem;
        background-color: rgb(249,249,254);
        border-radius: 5px;
        
    }
    li{
        list-style: none;
    }
    .icon-music {
        width: 20px;
        height: 20px;
        padding: 15px 15px;
        background-color: rgb(223,229,251);
        border-radius: 50%;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .selected {
        width: 100px;
        margin-left: 15px;
        text-align: center;
        position: relative;
    }
    .showSelect {
        position: absolute;
        top: -50px;
        left: 0;
        background-color: rgba(130,140,165,0.5);
    }

    .showSelect span{
        cursor: pointer;
        line-height: 2rem;
    }
    .showSelect span:hover {
        background-color: sandybrown;
    }
    .showSelect .title {
        color: red;
        line-height: 3rem;
    }
    .plan {
        color: rgb(47,56,88);
        font-weight: bold;
        line-height: 2rem;
    }
    .price {
        color: rgb(130,140,165);
    }
    .btn-change {
        width: -webkit-calc(100% - 150px);
        text-align: center;
        font-weight: bold;
        cursor: pointer;
        color: rgb(76,89,187);
    }
    .btn-change:hover {
        text-decoration: underline;
    }
    

</style>