<template>
    <div class='navbar'>
        <slot name="icon"></slot>
        <div class="p1">
            <slot name="sidebar"></slot>
        </div>
        <slot name="navgator"></slot>
        <slot name="searchbar"></slot>
    </div>
</template>

<script>

export default {
    name: "",
    data() {
        return {

        }
    },
}
</script>

<style scoped>
.navbar {
    height: 7vh;
    width: 100%;
    margin: auto;
    background-color: rgba(128, 128, 128, 0.484);
    position: fixed;
    top: 0;
    display: flex;
}

.p1 {
    height:100%;
    width:33%;
    display:flex;
    justify-content: center;
}
</style>