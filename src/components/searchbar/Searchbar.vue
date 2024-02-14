<template>
    <div class='search-bar'>
        <div class="icon-area">
            <Icon class="graph"></Icon>
        </div>
        <input class="input-area" placeholder="Search">

        </input>
    </div>
</template>

<script>
import Icon from "./icon.vue";

export default {
    name: "",
    data() {
        return {

        }
    },
    components: {
        Icon
    }
}
</script>

<style scoped>
.search-bar {
    height: 100%;
    width: 300px;
    margin: auto;
    background-color: rgb(255, 255, 255);
    border-radius: 50px;
    display: flex;    
    justify-content:center;
}


.input-area {
    width: 60%;
    height: 60%;    
    margin-top:auto;
    margin-bottom:auto;
    margin-left:0;    
    font-size: 2rem;
    border: none;
    border-bottom: 1px solid #000000;
}

.input-area:focus {
    outline: none;
}

.icon-area{
    height:100%;
    width:20%;
    display:flex;
    align-items: center
}

.graph {
    width: 50px;
    height: 50px;
}
</style>