<template>
  <select class="form-select" aria-label="Default select example">
    <option>-- --</option>
    <option v-for="(genre, i) in AlbumsGenres" :key="i" :value="genre" selected>{{ genre }}</option>
  </select>
</template>

<script>
export default {
  name: "BaseHeader",
  props: {
    AlbumsGenres: Array,
  },
};
</script>

<style lang="scss" scoped>
select {
  width: 200px;
  cursor: pointer;
}
</style>
