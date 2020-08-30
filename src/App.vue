<template>
  <div id="app">
    <main-page></main-page>
  </div>
</template>

<script>
import mainpage from "./components/Quotes/MainPage.vue";

export default {
  name: "App",
  components: {
    mainPage: mainpage,
  },
};
</script>

<style>
</style>
