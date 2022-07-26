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
  mounted() {
    axios("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.albums = res.data.response;
        console.log(this.albums);
      })
      .catch((err) => {
        console.error(err);
      });
  },
};
</script>

<style scoped lang="scss"></style>
