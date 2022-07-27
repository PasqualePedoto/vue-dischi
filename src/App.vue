<template>
  <div>
    <BaseHeader />
    <BaseMain :list-of-albums="albums" />
  </div>
</template>

<script>
import BaseHeader from "./components/BaseHeader.vue";
import BaseMain from "./components/BaseMain.vue";

// Importiamo axios per effettuare la chiamata
import axios from "axios";
export default {
  name: "App",
  components: {
    BaseHeader,
    BaseMain,
  },
  data() {
    return {
      albums: [],
      albumsGenres: [],
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
          // Preleviamo i generi
          this.getGenre();
        })
        .catch((err) => {
          console.error(err);
        })
        .then(() => {});
    },
    getGenre() {
      this.albumsGenres = this.albums.map((album) => album.genre);
      this.albumsGenres = this.deleteDuplicateArrayElement(this.albumsGenres);
    },
    deleteDuplicateArrayElement(array) {
      array = array.filter((genre, index) => array.indexOf(genre) === index);
      return array;
    },
  },
  mounted() {
    // Richiamiamo la funzione che al mounted di Vue preleva i dati
    this.getAlbumFromAPI(this.url);
  },
};
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
</style>
