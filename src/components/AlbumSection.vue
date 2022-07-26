<template>
  <section id="album-section">
    <ul class="d-flex flex-wrap g-3">
      <li></li>
    </ul>
  </section>
</template>

<script>
import axios from "axios";

export default {
  name: "AlbumSection",
  data() {
    return {
      albums: [],
    };
  },
};
</script>

<style scoped lang="scss"></style>
