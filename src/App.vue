<template>
  <div id="app">
    <MyHeader />
    <MyMain :url="apiUrl" />
  </div>
</template>

<script>
import MyHeader from "@/components/MyHeader.vue";
import MyMain from "@/components/MyMain.vue";

export default {
  name: "App",
  components: {
    MyHeader,
    MyMain,
  },
  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
    };
  },
};
</script>

<style lang="scss">
@import "@/style/utilities";

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: $main-font;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
