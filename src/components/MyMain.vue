<template>
  <div class="container">{{ url }}</div>
</template>

<script>
export default {
  name: "MyMain",
  props: {
    url: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss"></style>
