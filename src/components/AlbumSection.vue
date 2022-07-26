<template>
  <section id="album-section" class="w-100">
    <ul class="p-0 m-0 d-flex flex-wrap">
      <li v-for="(album, i) in ListOfAlbums" :key="i">
        <AlbumCard :album="album" />
      </li>
    </ul>
  </section>
</template>

<script>
import AlbumCard from "./AlbumCard.vue";
export default {
  name: "AlbumSection",
  components: {
    AlbumCard,
  },
  props: {
    ListOfAlbums: Array,
  },
};
</script>

<style scoped lang="scss">
#album-section {
  // Centriamo l'area dove risiederanno i dischi
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 50px 0;

  ul {
    width: 80%;

    li {
      width: calc(100% / 5 - 20px);
      padding: 10px;
      margin: 10px;

      background-color: #2e3a46;
    }
  }
}
</style>
