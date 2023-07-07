<template>
  <Header @open-page="page=$event"/>
  <a-carousel :style="{
    height: '100%',
    position: 'relative',
    zIndex: 1
  }" :after-change="onChange">
    <div class="banner-block" :style="{ height: '100%' }">
      <div class="banner-img" :style="{ background: 'url(/1631654667_18-phonoteka-org-p-pozhar-v-lesu-fon-krasivo-18.jpg)' }">
        <div class="banner-shadow" :style="{ height: '100%' }">
          <h1 class="banner-title dynamic-text-fast" :class="{
            'hide-text': carousel_page != 0,
            'show-text-fast': carousel_page == 0
          }">Тушение лесных пожаров</h1>
          <div class="banner-text dynamic-text-long" :class="{
            'hide-text': carousel_page != 0,
            'show-text-long': carousel_page == 0
          }">
            <p>
              Лесные пожары - это очень серьезная проблема по многим причинам. По мимо того, что огонь может навредить инфраструктуре и человеку, это стихия очень сильно вредит природе. Нам нужно помнить, что мы часть этой природы, и наш долг сохранить эти чудесные леса для следующих поколений.
            </p>
          </div>
          <!--<div class="banner-info">
            <p>
              Если вы обнаружили очаг возгарания или уже действующий пожар, звоните по телефону <a>+7900000000</a>, или оставьте <a>заявку для звонка</a>
            </p>
          </div>-->
          <div class="banner-button dynamic-text-long dynamic-swim-out" :class="{
            'hide-text': carousel_page != 0,
            'show-text-long': carousel_page == 0,
            'dynamic-swim-out-end': carousel_page == 0
          }" @click="page=1">Перейти к услуги</div>
        </div>
      </div>
    </div>
    <div class="banner-block" :style="{ height: '100%' }">
      <div class="banner-img" :style="{ background: 'url(/104484-2.jpg)' }">
        <div class="banner-shadow" :style="{ height: '100%' }">
          <h1 class="banner-title dynamic-text-fast" :class="{
            'hide-text': carousel_page != 1,
            'show-text-fast': carousel_page == 1
          }">Восстановление лесов</h1>
          <div class="banner-text dynamic-text-long" :class="{
            'hide-text': carousel_page != 1,
            'show-text-long': carousel_page == 1
          }">
            <p>
              Содействие естественному возобновлению проводится на тех площадях, где восстановление хозяйственно ценных пород можно обеспечить путём сохранения подроста или минерализации почвы
            </p>
          </div>
          <!--<div class="banner-info">
            <p>
              Если вы обнаружили очаг возгарания или уже действующий пожар, звоните по телефону <a>+7900000000</a>, или оставьте <a>заявку для звонка</a>
            </p>
          </div>-->
          <div class="banner-button dynamic-text-long dynamic-swim-out" :class="{
            'hide-text': carousel_page != 1,
            'show-text-long': carousel_page == 1,
            'dynamic-swim-out-end': carousel_page == 1
          }">Перейти к услуги</div>
        </div>
      </div>
    </div>
  </a-carousel>
  <div class="page" :class="{ 'page-open': page == 1 }">
    <div class="page-head">
      <CloseOutlined @click="page=null"/>
    </div>
    <h1 class="page-title">Тушение лесных пожаров</h1>
    <div class="page-text">
      <p>
        Лесные пожары - это очень серьезная проблема по многим причинам. По мимо того, что огонь может навредить инфраструктуре и человеку, это стихия очень сильно вредит природе. Нам нужно помнить, что мы часть этой природы, и наш долг сохранить эти чудесные леса для следующих поколений.
      </p>
    </div>
  </div>
</template>
<script setup lang="ts">
  import { ref } from 'vue'
  import { CloseOutlined } from '@ant-design/icons-vue'
  import Header from './components/Header.vue';
  
  const page = ref<number | null>(null)

  const carousel_page = ref<number | null>(null)
  setTimeout(()=>carousel_page.value = 0, 500)
  const onChange = (page: number) => {
    carousel_page.value = page
  }

</script>
<style scoped>
.page-head {
    display: flex;
    justify-content: flex-end;
    padding: 20px;
}
.page-text{
    line-height: normal;
    text-align: initial;
    padding: 30px;
    font-size: 16px;
}
.page {
    position: absolute;
    width: calc(100% - 30px);
    height: calc(100% - 95px);
    background: white;
    z-index: 0;
    transition: all 500ms;
    opacity: 0;
    margin: 15px;
    border-radius: 10px;
    display: block;
    margin-top: 80px;
    top: 0px;
}
.page-open {
    opacity: 1;
    z-index: 9998;
}
.page-title{
    font-size: 30px;
    text-align: left;
    padding: 30px;
    font-family: PlayfairDisplay;
    text-align: center;
}
.ant-carousel :deep(.slick-slide) {
  text-align: center;
  height: 100%;
  line-height: 160px;
  background: #364d79;
  overflow: hidden;
}
.ant-carousel :deep(.slick-initialized) {
  height: 100%;
}

.ant-carousel :deep(.slick-list) {
  height: 100%;
}

.ant-carousel :deep(.slick-track) {
  height: 100%;
}

.ant-carousel :deep(.slick-slide h3) {
  color: #fff;
}
.ant-carousel :deep(.slick-slide>div) {
  height: 100%;
}
.banner-img{
  height: 100%;
  background-size: cover!important;
  background-position-x: center!important;
}

.banner-block{
  height: 100%;
}

h1.banner-title {
    color: white;
    font-size: 28px;
    text-align: left;
    padding: 30px;
    padding-top: 100px;
    font-family: PlayfairDisplay;
}
.page-title{
    font-size: 30px;
    text-align: left;
    padding: 30px;
    font-family: PlayfairDisplay;
    text-align: center;
}
.banner-shadow {
    height: 100%;
    background: #020202a6;
}
.banner-text {
    line-height: normal;
    text-align: initial;
    color: #e1e1e1;
    padding: 30px;
    font-size: 16px;
}
.banner-button {
  /*border: 1px solid #ffffff;*/
  line-height: normal;
  /*padding: 10px;*/
  color: #ffffff;
  margin: 20px;
  border-radius: 7px;
  transition: background 200ms;
  width: 65%;
  text-align: left;
  font-size: 18px;
  text-decoration: underline;
  margin-left: 40px;
}
.banner-button:hover {
  background: #ffffff61;
}
.dynamic-text-fast{
  opacity: 0;
  transition: all 1000ms;
}
.show-text-fast {
  opacity: 1;
}
.dynamic-text-long{
  opacity: 0;
  transition: all 1000ms;
  transition-timing-function: cubic-bezier(0.91, -0.18, 1, 1);
}
.show-text-long {
  opacity: 1;
}
.hide-text {
  opacity: 0;
  transition-duration: 0ms;
}
.dynamic-swim-out{
  margin-top: 50px;
  transition: all 1000ms;
  transition-timing-function: cubic-bezier(0.91, -0.18, 1, 1);
}
.dynamic-swim-out-end{
  margin-top: 20px;
}
</style>
