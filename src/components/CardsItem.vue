<template>
  <div class="img_container text-white">
    <img :src="song.poster" alt="" class="w-100" />
    <div class="title-song">
      <h3 class="font_size">{{ song.title }}</h3>
    </div>
    <div class="text_card">
      <p>{{ song.author }}</p>

      <p>{{ song.year }}</p>
    </div>
  </div>
</template>

<script>
export default {
  nome: "CardsItem",
  props: {
    song: Object,
  },
};
</script>
<style scoped lang="scss">
@import "@/style/utilities";

.img_container {
  background-color: $bg-header;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  flex-wrap: wrap;
}
.text_card {
  color: $text-color-card;
  padding-top: 15px;
  p {
    line-height: 0px;
  }
}
.font_size {
  font-size: 24px;
  padding-top: 5px;
  font-weight: 700;
}
</style>
