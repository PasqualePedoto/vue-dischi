<template>
  <div>
    <BaseHeader :albums-genres="albumsGenres" :authors="authors" @genre-selected="changeGenre" @author-selected="changeAuthor" />
    <BaseMain :list-of-albums="filterAlbums" />
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
      filterAlbums: [],
      albumsGenres: [],
      genre: "",
      authors: [],
      url: "https://flynn.boolean.careers/exercises/api/array/music",
    };
  },
  methods: {
    // Metodo che preleva i dati forniti da una precisa API passata
    // come parametro
    getAlbumFromAPI(url) {
      axios(url)
        .then((res) => {
          this.filterAlbums = this.albums = res.data.response;
          // Preleviamo i generi
          this.getGenre();
          this.getAuthors();
        })
        .catch((err) => {
          console.error(err);
        })
        .then(() => {});
    },

    //Metodo che elimina tutti i dublicati di un array
    deleteDuplicateArrayElement(array) {
      array = array.filter((genre, index) => array.indexOf(genre) === index);
      return array;
    },

    // Metodo che genera un array contenenti tutti gli autori distinti
    // così da passarli al BaseSelect che genererà una selezione
    // basata su questi
    getAuthors() {
      this.albumsGenres = this.albums.map((album) => album.genre);
      this.albumsGenres = this.deleteDuplicateArrayElement(this.albumsGenres);
    },
    //Cambio dell'autore in seguito alla scelta della select
    changeAuthor(author) {
      this.author = author;
    },

    // Metodo che genera un array contenenti tutti i generi distinti
    // così da passarli al BaseSelect che genererà una selezione
    // basata su questi
    getGenre() {
      this.authors = this.albums.map((album) => album.author);
      this.authors = this.deleteDuplicateArrayElement(this.authors);
    },
    //Cambio del genere in seguito alla scelta della select
    changeGenre(genre) {
      this.genre = genre;

      if (this.genre === "") this.filterAlbums = this.albums.map((album) => album);
      else this.filterAlbums = this.albums.filter((album) => album.genre === this.genre);
    },
  },
  computed: {},
  mounted() {
    // Richiamiamo la funzione che al mounted di Vue preleva i dati
    this.getAlbumFromAPI(this.url);
  },
};
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
</style>
