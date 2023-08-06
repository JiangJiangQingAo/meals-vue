<script setup>
import Meal from './Meal.vue';

const props = defineProps(["meals"])
</script>
<template>
    <div class="meals">
        <Meal :desc="$attrs.desc" v-for="item in props.meals" :meal = "item"></Meal>
        <template v-if="!props.meals || props.meals.length === 0 ">
            <h2>没有找到商品</h2>
        </template>
    </div>
</template>
<style scoped>
.meals{
    height: calc(100vh - 122rem);
    /* padding: 120rem 0; */
    padding-bottom: 140rem;
    overflow: auto;
}
</style>