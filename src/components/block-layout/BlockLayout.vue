<template>
    <div class='block-layout'>
        <slot name="elements">
        </slot>
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
.block-layout {
    width: 100%;
    height: 100%;
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

@media screen and (min-width: 350px) {
    .block-layout:first-child {
        flex-grow: 1;
    }
}

@media screen and (min-width: 700px) {
    .block-layout:first-child {
        flex-grow: 2;
    }
}

@media screen and (min-width: 1050px) {
    .block-layout:first-child {
        flex-grow: 3;
    }
}

@media screen and (min-width: 1400px) {
    .block-layout:first-child {
        flex-grow: 4;
    }
}

@media screen and (min-width: 1750px) {
    .block-layout:first-child {
        flex-grow: 5;
    }
}
</style>