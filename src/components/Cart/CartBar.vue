<script setup>
import { ref } from "vue";
import cartBag from "../../assets/bag.png"
import { useMealsStore } from "../../store/meals";
import CartDetails from "./CartDetails.vue";
const meals = useMealsStore()
const showDetails = ref(false)
</script>
<template>
    <CartDetails :is-show="showDetails" @hide="showDetails=false"></CartDetails>
    <div class="cart-bar">
        <div class="cart-bag">
            <img :src="cartBag" alt="/">
            <span v-show="meals.totalCount>0" class="total-count">{{ meals.totalCount }}</span>
        </div>
        <div class="total-amount">
            <p v-show="meals.totalCount<=0" class="no-goods">未选购商品</p>
            <p v-show="meals.totalCount>0" class="has-goods" @click="showDetails=true">{{ meals.amount }}</p>
        </div>
        <button class="checkout">去结算</button>
    </div>
</template>
<style scoped>
    .cart-bar{
        position: fixed;
        background-color: rgb(58, 58, 58);
        bottom: 40rem;
        width: 710rem;
        left: 0;
        right: 0;
        margin: 0 auto;
        height: 100rem;
        border-radius: 60rem;
        z-index: 9999;
    }
    .cart-bag{
        width: 100rem;
        position: absolute;
        bottom: -10rem;
    }
    .total-count{
        position: absolute;
        background-color: red;
        border-radius: 50%;
        right: -20rem;
        width: 40rem;
        text-align: center;
        line-height: 40rem;
        height: 40rem;
        color: #fff;
        font-weight: bold;
    }
    .total-amount{
        margin-left: 160rem;
        line-height: 100rem;        
    }
    .no-goods,.has-goods{
        color: rgb(148, 148, 148);
        font-size: 36rem;
        font-weight: bold;
    }
    .has-goods{
        color: #fff;
    }
    .has-goods::before{
        content: '￥';
        font-size: 26rem;
    }
    .checkout{
        position: absolute;
        top: 0;
        right: 0;
        width: 200rem;
        height: 100%;
        border-radius: 60rem;
        border: none;
        background-color: rgb(248, 188, 0);
        font-size: 36rem;
    }
</style>