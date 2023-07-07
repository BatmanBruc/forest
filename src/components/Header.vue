<template>
    <header>
        <div class="button-phone">

        </div>
        <div class="button-menu">
            <div>
                <div id="nav-icon1" :class="{
                    open: isOpen
                }" @click="isOpen=!isOpen">
                    <span></span>
                    <span></span>
                    <span></span>
                </div>
            </div>
        </div>
    </header>
    <a-drawer
        v-model:visible="isOpen"
        width="100%"
        :closable="false"
        :style="{
            zIndex: 9999
        }"
    >
    <div class="contacts">
        <div class="contacts-item">
            <PhoneOutlined :style="{ marginRight: '10px' }"/>
            <span>+79644507014</span>
        </div>
        <div class="contacts-item">
            <EnvironmentOutlined :style="{ marginRight: '10px' }" />
            <span>г. Артем Пушкино 1</span>
        </div>
    </div>
    <div class="menu">
        <div class="menu-item" @click="emit('openPage', 1);isOpen=false">Тушение лесных пожаров</div>
        <div class="menu-item" @click="emit('openPage', 2);isOpen=false">Восстановление лесов</div>
    </div>
  </a-drawer>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
import { PhoneOutlined, EnvironmentOutlined } from '@ant-design/icons-vue'

const emit = defineEmits(['openPage'])
const isOpen = ref(false)
</script>

<style>
.menu {
    margin-top: 100px;
}
header{
    position: absolute;
    z-index: 10000;
    width: 100%;
    padding: 20px;
}
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
    background: white;
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
.ant-drawer-body {
    flex-grow: 1;
    padding: 24px;
    overflow: auto;
    font-size: 14px;
    line-height: 1.5715;
    word-wrap: break-word;
    background: #795548;
}
.menu {
    margin-top: 40px;
}
.menu-item {
    font-size: 22px;
    margin-bottom: 20px;
    color: #ffffff;
}
.contacts {
    margin-top: 100px;
    display: flex;
    justify-content: space-around;
}
.contacts-item {
    font-size: 15px;
    margin-bottom: 20px;
    color: #352d2a;
}
</style>