<script setup>
    import Mask from '../UI/Mask.vue';
    import Meals from '../Meals/Meals.vue';
import { useMealsStore } from '../../store/meals';
    const meals = useMealsStore()
</script>
<template>
    <Mask>
        <div class="cart-details">
         <div class="header">
            <h2>餐品详情</h2>
            <a href="javascript:;">
                <i class="ri-delete-bin-line"></i>
                清空购物车
            </a>
         </div>
         <Meals :desc="false" :meals="meals.cartMeals"></Meals>
        </div>
    </Mask>
    
</template>

<style scoped>
    .cart-details{
        background-color: #fff;
        position: absolute;
        bottom: 0;
        width: 100%;
        border-top-left-radius: 40rem;
        border-top-right-radius: 40rem;
    }
    .meals{
        max-height: calc(280rem*4);
        height: auto;
    }
    .header{
        display: flex;
        justify-content: space-between;
        padding: 20rem 40rem;
        background-color: #fff;
    }
    .header h2{
        font-size: 28rem;
    }
    .header a{
        color: #9f9f9f;
        font-size: 26rem;
    }
    .header i{
        margin-right: 5rem;
    }
</style>