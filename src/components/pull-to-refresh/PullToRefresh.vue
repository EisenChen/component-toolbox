<template>
    <div class='pull-to-refresh'>
        <Refresh id="refresh-spin" class="refresh-spin"></Refresh>
    </div>
</template>

<script>
import Refresh from './refresh.vue';

export default {
    name: "",
    components: {
        Refresh
    },
    data() {
        return {
            slideIn: "-40px"
        }
    },
    mounted() {
        let touchstartY = 0;
        document.addEventListener('touchstart', e => {
            touchstartY = e.touches[0].clientY;
        });
        document.addEventListener('touchmove', e => {
            const touchY = e.touches[0].clientY;
            const touchDiff = touchY - touchstartY;
            if (touchDiff > 0 && window.scrollY === 0) {
                document.getElementById('refresh-spin').classList.add('fade-in');
                this.slideIn = Number(-40 + touchDiff).toString() + "px";
                e.preventDefault();
            }
        });
        document.addEventListener('touchend', e => {
            if (document.getElementById('refresh-spin').classList.contains('fade-in')) {
                document.getElementById('refresh-spin').classList.remove('fade-in')
                this.$emit('refresh', true);
            }
        });
    }
}
</script>

<style>
body {
    overscroll-behavior: none;
}

.refresh-spin {
    display: none;
    position: fixed;
    top: v-bind(slideIn);
    left: calc(50% - 20px);
    height: 40px;
    width: 40px;
}

.fade-in {
    display: block;
    animation: showUp 1s linear, spin 1.1s linear;
    animation-iteration-count: 1, infinite;
}

@keyframes spin {
    0% {
        -webkit-transform: rotate(0deg);
        transform: rotate(0deg);
    }

    100% {
        -webkit-transform: rotate(360deg);
        transform: rotate(360deg);
    }
}

@keyframes showUp {
    0% {
        opacity: 0;
    }

    100% {
        opacity: 100%;
    }
}
</style>