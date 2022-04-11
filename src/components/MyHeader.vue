<template>
  <header>
    <div class="container-fluid">
      <div class="row">
        <div class="col-12">
          <div class="logo-img p-2">
            <img alt="Logo Spotify" src="../assets/spotify.png" class="w-50" />
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "MyHeader",
  props: {
    genreOut: Array,
  },
  data() {
    return {
      genreSelected: "",
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "@/style/utilities";

header {
  background-color: $bg-header;
}
.logo-img {
  width: 10%;
}
</style>
