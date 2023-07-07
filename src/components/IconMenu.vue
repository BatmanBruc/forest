<template>
    <div>
        <div id="nav-icon1" :class="{
            open: isOpen
        }" @click="isOpen=!isOpen">
            <span></span>
            <span></span>
            <span></span>
        </div>
    </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const isOpen = ref(false)
</script>

<style>
#nav-icon1 {
    width: 35px;
    height: 45px;
    position: relative;
    transform: rotate(0deg);
    transition: .5s ease-in-out;
    cursor: pointer;
}
#nav-icon1 span {
    display: block;
    position: absolute;
    height: 4px;
    width: 100%;
    background: white;
    border-radius: 9px;
    opacity: 1;
    left: 0;
    transform: rotate(0deg);
    transition: .25s ease-in-out;
}
#nav-icon1.open span {
    background: rgb(70, 70, 70);
}
#nav-icon1 span:nth-child(1) {
    top: 6px;
}
#nav-icon1 span:nth-child(2) {
    top: 18px;
}
#nav-icon1 span:nth-child(3) {
    top: 30px;
}
#nav-icon1.open span:nth-child(1) {
    top: 18px;
    transform: rotate(135deg);
}
#nav-icon1.open span:nth-child(2) {
    opacity: 0;
    left: -60px;
}
#nav-icon1.open span:nth-child(3) {
    top: 18px;
    transform: rotate(-135deg);
}
</style>