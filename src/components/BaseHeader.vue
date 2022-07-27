<template>
  <section class="p-0 container">
    <header>
      <figure class="m-0"><img class="img-fluid m-3" src="../assets/image/logo.svg" alt="spotify-logo" /></figure>
      <BaseSelect :array="AlbumsGenres" @selected="choiceSelected" />
      <BaseSelect :array="authors" @selected="choiceSelected" />
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
    authors: Array,
  },
  methods: {
    choiceSelected(element) {
      this.genre = element;
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
