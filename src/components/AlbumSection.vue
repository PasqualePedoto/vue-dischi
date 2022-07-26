<template>
  <section id="album-section" class="w-100">
    <ul class="p-0 m-0 d-flex flex-wrap">
      <li v-for="(album, i) in albums" :key="i">
        <figure class="m-0">
          <img class="img-fluid h-100 w-100" :src="album.poster" :alt="album.title" />
        </figure>
        <div id="caption" class="align-content-between text-center">
          <h4 class="m-0 mt-3 mb-5 text-white">{{ album.title }}</h4>
          <div class="mt-3">
            <p class="m-0 text-gray">{{ album.author }}</p>
            <p class="m-0 text-gray">{{ album.year }}</p>
          </div>
        </div>
      </li>
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

<style scoped lang="scss">
#album-section {
  // Centriamo l'area dove risiederanno i dischi
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 50px 0;

  ul {
    width: 80%;

    li {
      width: calc(100% / 5 - 20px);
      padding: 10px;
      margin: 10px;

      background-color: #2e3a46;

      figure {
        width: 100%;
        height: 160px;
      }

      #caption {
        display: flex;
        flex-direction: column;
        justify-content: space-between;

        h4 {
          height: 50px;
        }
        p {
          color: #7d7f7a;
        }
      }
    }
  }
}
</style>
