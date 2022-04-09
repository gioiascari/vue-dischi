<template>
  <div class="container padding_top">
    <div class="row text-center justify-content-between">
      <CardsItem
        :song="item"
        v-for="(item, i) in songs"
        :key="i"
        class="w_20 p-3"
      />
    </div>
  </div>
</template>

<script>
import CardsItem from "@/components/CardsItem.vue";
import axios from "axios";
export default {
  name: "MyMain",
  data() {
    return {
      songs: [],
    };
  },

  components: {
    CardsItem,
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        if (response.status === 200) {
          this.songs = response.data.response;
          console.log(this.songs);
        }
      });
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "@/style/utilities";

.w_20 {
  width: 18%;
  margin-bottom: 20px;
}
.padding_top {
  padding-top: 58px;
}
</style>
