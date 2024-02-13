<template>
    <div class='paginator'>
        <Left_end class="graph linkable" v-if="currentPage != 1"></Left_end>
        <left class="graph linkable" v-if="currentPage != 1"></left>
        <div class="page-number linkable" v-if="currentPage - 2 > 1" @click="$emit('toPage', 1)">1</div>
        <Dots class="graph" v-if="currentPage - 3 > 1"></Dots>
        <div class="page-number linkable" v-if="currentPage + 1 > totalPage" @click="$emit('toPage', currentPage - 4)">{{
            currentPage - 4 }}</div>
        <div class="page-number linkable" v-if="currentPage + 2 > totalPage" @click="$emit('toPage', currentPage - 3)">{{
            currentPage - 3 }}</div>
        <div class="page-number linkable" v-if="currentPage - 2 > 0" @click="$emit('toPage', currentPage - 2)">{{
            currentPage
            - 2 }}</div>
        <div class="page-number linkable" v-if="currentPage - 1 > 0" @click="$emit('toPage', currentPage - 1)">{{
            currentPage
            - 1 }}</div>
        <div class="page-number curr-p">{{ currentPage }}</div>
        <div class="page-number linkable" v-if="currentPage + 1 <= totalPage" @click="$emit('toPage', currentPage + 1)">{{
            currentPage + 1 }}</div>
        <div class="page-number linkable" v-if="currentPage + 2 <= totalPage" @click="$emit('toPage', currentPage + 2)">{{
            currentPage + 2 }}</div>
        <div class="page-number linkable" v-if="currentPage - 2 < 1" @click="$emit('toPage', currentPage + 3)">{{
            currentPage +
            3 }}</div>
        <div class="page-number linkable" v-if="currentPage - 1 < 1" @click="$emit('toPage', currentPage + 4)">{{
            currentPage
            + 4 }}</div>
        <Dots class="graph" v-if="currentPage + 3 < totalPage"></Dots>
        <div class="page-number linkable" v-if="currentPage + 2 < totalPage" @click="$emit('toPage', totalPage)">{{
            totalPage
        }}</div>
        <Right class="graph linkable" v-if="currentPage != totalPage"></Right>
        <Right_end class="graph linkable" v-if="currentPage != totalPage"></Right_end>
    </div>
</template>

<script setup>
import Dots from "./assets/dots.vue";
import left from "./assets/left.vue";
import Left_end from "./assets/left_end.vue";
import Right from "./assets/right.vue";
import Right_end from "./assets/right_end.vue";

const props = defineProps({
    totalPage: Number,
    currentPage: Number,
})


</script>

<style scoped>
.paginator {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;

    margin: auto;

    background-color: rgb(225, 225, 225);
}

.graph {
    width: 50px;
    height: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.page-number {
    width: 50px;
    height: 50px;
    font-size: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 50px;
}

.curr-p {
    color: white;
    background-color: rgb(129, 0, 181);
}

.linkable:hover {
    cursor: pointer;
    background-color: rgb(209, 92, 255);
}
</style>