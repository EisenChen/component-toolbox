<template>
    <Icon class="open" v-if="!opened" @click="opened = !opened"></Icon>
    <Transition name="slide">
        <div id='sidebar' class='sidebar' v-if="opened">
            <Close class="close" @click="$emit('closed', true)"></Close>
        </div>
    </Transition>
</template>

<script>
import Close from './close.vue'
import Icon from './sidebar-icon.vue'

export default {    
    props: {
        opened: Boolean
    },
    components: {
        Close,
        Icon
    }
}
</script>

<style scoped>
.sidebar {
    min-height: 100vh;
    min-width: 350px;
    height: 100%;
    background-color: rgba(128, 128, 128, 0.5);
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
}

.slide-enter-active,
.slide-leave-active {
    transition: all 1s;
}

.slide-enter-from,
.slide-leave-to {
    left: -350px;
}

.slide-enter-to,
.slide-leave-from {
    left: 0;
}

.open {
    height: 50px;
    width: 50px;
    cursor: pointer;
    margin: auto;
}

.close {
    height: 50px;
    width: 50px;
    position: absolute;
    right: 1rem;
    top: 1rem;
    cursor: pointer;
}
</style>