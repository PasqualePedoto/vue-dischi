<template>
  <main class="container">
    <AlbumSection />
  </main>
</template>

<script>
import AlbumSection from "./AlbumSection.vue";
export default {
  name: "BaseMain",
  components: {
    AlbumSection,
  },
};
</script>

<style lang="scss" scoped>
main {
  background-color: #1e2d3b;

  // Centriamo l'area dove risiederanno i dischi
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
