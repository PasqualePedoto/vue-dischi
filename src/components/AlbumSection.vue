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
      url: "https://flynn.boolean.careers/exercises/api/array/music",
    };
  },
  methods: {
    // Metodo che preleva i dati forniti da una precisa API passata
    // come parametro
    getAlbumFromAPI(url) {
      axios(url)
        .then((res) => {
          this.albums = res.data.response;
          console.log(this.albums);
        })
        .catch((err) => {
          console.error(err);
        })
        .then(() => {});
    },
  },
  mounted() {
    // Richiamiamo la funzione che al mounted di Vue preleva i dati
    this.getAlbumFromAPI(this.url);
  },
};
</script>

<style scoped lang="scss"></style>
