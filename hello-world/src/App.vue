<template>
  <div id="app">
    {{message}}
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  mounted() {
    setTimeout(() => {
      this.test();
    }, 3000);
  },
  data() {
    return {
      message: '12345',
    }
  },
  methods: {
    test() {
      this.message = 'new message';
      console.log(this.$el.textContent);
      this.$nextTick(function () {
        console.log(this.$el.textContent)
      })
    },
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
