<script setup>
import Counter from '../UI/Counter.vue';

    const props = defineProps(["meal","desc"])
    // const meal = props.meal
</script>
<template>
    <div class="meal">
        <div class="img">
            <img :src="props.meal.img" alt="meal.tatle">
        </div>
        <div class="info">
            <div class="desc">
                <h2>{{ props.meal.title }}</h2>
                <p v-show="desc">{{ props.meal.desc }}</p>
            </div>
            <div class="price-btn">
                <span class="price">{{ props.meal.price }}</span>
                <Counter :meal="props.meal"></Counter>
            </div>
            <!-- 
            {{ meal.price }} -->
        </div>
    </div>
</template>
<style scoped>
    .meal{
        height: 280rem;
        display: flex;
        align-items: center;
        padding: 0 20rem;
        border-bottom: 1px #e6e6e6 solid;
    }
    .img{
        width: 200rem;
    }
    .info{
        width: 450rem;
        margin-left: 20rem;
    }
    .info h2{
        color: #000;
        font-size: 30rem;
        font-weight: normal;
    }
    .info p{
        font-size: 24rem;
        color: #9f9f9f;
    }
    .price-btn{
        display: flex;
        justify-content: space-between;
        margin-top: 40rem;
    }
    .price{
        font-size: 30rem;
        font-weight: bold;
    }
    .price::before{
        content: '￥';
    }
</style>