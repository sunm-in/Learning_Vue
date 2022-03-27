<template>
  <div class="menu">
    <a v-for="(a, i) in menuName" :key="i">{{ a }}</a>
  </div>

  <div v-for="(item, key) in products" :key="key">
    <h4>
      {{ item }}
    </h4>
    <p>50 만원</p>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      menuName: ['Home', 'Shop', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
      price: ['50', '60', '70'],
    };
  },
  components: {},
};
</script>

<style>
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
