<template>
    <div id="scroll-to-top" v-if="yPos > 0" @click="backToTop">
        <Arrow class="icon"></Arrow>
    </div>
</template>

<script>
import Arrow from './arrow.vue';

export default {
    components: { Arrow },
    data() {
        return {
            yPos: 0,
        }
    },
    created() {
        window.addEventListener("scroll", this.handleScroll);
    },
    methods: {
        handleScroll() {
            this.yPos = window.scrollY;
        },
        backToTop() {
            window.scrollTo({
                top: 0,
                left: 0,
                behavior: "smooth",
            });
        }
    }
}
</script>

<style scoped>
#scroll-to-top {
    width: 75px;
    height: 75px;
    background-color: gray;
    border-radius: 50px;
    display: flex;
    align-items: center;
    justify-content: center;

    position: fixed;
    bottom: 2rem;
    right: 4rem;
    cursor: pointer;
}

.scroll-to-top:hover {
    background-color: rgb(162, 162, 162);
}

.icon {
    width: 75%;
    height: 75%;
}
</style>