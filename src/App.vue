<template>
  <div id="app">
    <!--img alt="Vue logo" src="./assets/logo.png" /-->
    <MyHeader />
    <MyMain />
  </div>
</template>

<script>
import MyHeader from "./components/MyHeader.vue";
import MyMain from "./components/MyMain.vue";

export default {
  name: "App",
  components: {
    MyHeader,
    MyMain,
  },
};
</script>

<style lang="scss">
@import "@/style/utilities";

#app {
  font-family: $main-font;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
