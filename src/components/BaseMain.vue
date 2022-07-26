<template>
  <main class="container">
    <AlbumSection :list-of-albums="ListOfAlbums" />
  </main>
</template>

<script>
import AlbumSection from "./AlbumSection.vue";
export default {
  name: "BaseMain",
  components: {
    AlbumSection,
  },
  props: {
    ListOfAlbums: Array,
  },
};
</script>

<style lang="scss" scoped>
main {
  background-color: #1e2d3b;
}
</style>
