<template>
  <div class="black-bg" v-if="isActive === true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="isActive = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(item, key) in menuName" :key="key">{{ item }}</a>
  </div>

  <!-- <div v-for="(item, key) in products" :key="key">
    <h4>{{ item }}</h4>
    <p>50 만원</p>
  </div> -->

  <div v-for="(item, key) in room" :key="key">
    <img :src="item.image" class="room-img" />
    <h4 @click="isActive = true">{{ item.title }}</h4>
    <p>{{ item.price }}만원</p>
  </div>

  <!-- <div>
    <img src="./assets/images/room1.jpg" class="room-img" />
    <h4>{{ products[1] }}</h4>
    <p>50만원</p>
    <button @click="reportCount[1] += 1">허위매물 신고</button>
    <span>신고수: {{ reportCount[1] }}</span>
  </div>
  <div>
    <img src="./assets/images/room2.jpg" class="room-img" />
    <h4>{{ products[2] }}</h4>
    <p>50만원</p>
    <button @click="reportCount[2] += 1">허위매물 신고</button>
    <span>신고수: {{ reportCount[2] }}</span>
  </div> -->
</template>

<script>
import { dummyData } from './assets/oneroom.js';

export default {
  name: 'App',
  data() {
    return {
      room: dummyData,
      isActive: false,
      reportCount: [0, 0, 0],
      menuName: ['Home', 'Shop', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
      price: ['50', '60', '70'],
    };
  },
  methods: {
    increase() {
      this.reportCount += 1;
    },
  },

  components: {},
};
</script>

<style>
body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.room-img {
  width: 70%;
  height: 400px;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
