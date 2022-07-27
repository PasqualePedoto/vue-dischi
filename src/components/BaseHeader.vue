<template>
  <section class="p-0 container">
    <header>
      <figure class="m-0"><img class="img-fluid m-3" src="../assets/image/logo.svg" alt="spotify-logo" /></figure>
      <BaseSelect :array="AlbumsGenres" @selected="genreSelected" />
      <BaseSelect :array="authors" @selected="authorSelected" />
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
      author: "",
    };
  },
  props: {
    AlbumsGenres: Array,
    authors: Array,
  },
  methods: {
    genreSelected(element) {
      this.genre = element;
      this.$emit("genre-selected", this.genre);
    },
    authorSelected(element) {
      this.author = element;
      this.$emit("author-selected", this.author);
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
