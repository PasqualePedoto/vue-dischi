<template>
  <section class="p-0 container">
    <header>
      <figure class="m-0"><img class="img-fluid m-3" src="../assets/image/logo.svg" alt="spotify-logo" /></figure>
      <BaseSelect :albums-genres="AlbumsGenres" @genre-selected="genreSelected" />
    </header>
  </section>
</template>

<script>
import BaseSelect from "./BaseSelect.vue";
export default {
  name: "BaseHeader",
  components: { BaseSelect },
  data() {
    return {
      genre: "",
    };
  },
  props: {
    AlbumsGenres: Array,
  },
  methods: {
    genreSelected(genre) {
      this.genre = genre;
      this.$emit("genre-selected", this.genre);
    },
  },
};
</script>

<style scoped lang="scss">
header {
  background-color: #2e3a46;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-right: 20px;

  figure {
    width: 150px;
  }
}
</style>
