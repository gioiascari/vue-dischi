<template>
  <div class="container padding_top">
    <div class="row text-center justify-content-between">
      <SelectedBar @selectionChanged="getSelectionValue" />
      <CardsItem
        :song="item"
        v-for="(item, i) in filteredAlbums()"
        :key="i"
        class="w_20 p-3"
      />
    </div>
  </div>
</template>

<script>
/*author: (...)
genre: (...)
poster: (...)
title: (...)
year: (...) */
import CardsItem from "@/components/CardsItem.vue";
import SelectedBar from "@/components/SelectedBar.vue";
import axios from "axios";
export default {
  name: "MyMain",

  data() {
    return {
      songs: [],
      selectionValue: "",
    };
  },

  components: {
    CardsItem,
    SelectedBar,
  },
  methods: {
    getSelectionValue: function (selectedValue) {
      this.selectionValue = selectedValue;
    },
    filteredAlbums: function () {
      if (this.selectionValue === "") {
        return this.songs;
      }
      const filteredArray = this.songs.filter((album) => {
        return album.genre === this.selectionValue;
      });

      return filteredArray;
    },
  },
  created: function () {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.songs = response.data.response;
        console.log(this.songs);
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
