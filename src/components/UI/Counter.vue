<script setup>
    import {ref} from 'vue'
    import { useMealsStore } from '../../store/meals';
    const meals = useMealsStore()
    const props = defineProps(["meal"])
</script>
<template>
    <div class="counter">
        <template v-if="props.meal.count>0">
            <button class="sub" @click="meals.subMealFromCart(props.meal)"><i class="ri-subtract-line"></i></button>
            <span class="count">{{ props.meal.count }}</span>
        </template>
        
        <button class="add" @click="meals.addMealToCart(props.meal)"><i class="ri-add-line"></i></button>
    </div>
</template>
<style scoped>
    .counter{
        display: flex;
        align-items: center;
    }
    
    .sub, .add{
        width: 36rem;
        height: 36rem;
        display: flex;
        align-items: center;
        justify-content: center;
        background-color: rgb(234, 178, 0);
        border-radius: 50%;
        border: none;
        font-size: 36rem;
    }
    .sub{
        background-color: #fff;
        border:1px solid #000
    }
    .count{
        font-size: 30rem;
        margin: 0 10rem;
    }
</style>