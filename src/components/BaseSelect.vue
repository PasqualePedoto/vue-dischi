<template>
  <select v-model="genreSelected" class="form-select" @change="emitGenre" aria-label="Default select example">
    <option value="" selected>-- --</option>
    <option v-for="(genre, i) in AlbumsGenres" :key="i" :value="genre">{{ genre }}</option>
  </select>
</template>

<script>
export default {
  name: "BaseHeader",
  props: {
    AlbumsGenres: Array,
  },
  data() {
    return {
      genreSelected: "",
    };
  },
  methods: {
    emitGenre() {
      this.$emit("genre-selected", this.genreSelected);
    },
  },
};
</script>

<style lang="scss" scoped>
select {
  width: 200px;
  cursor: pointer;
}
</style>
