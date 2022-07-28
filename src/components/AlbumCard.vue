<template>
  <section id="album-card">
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
  </section>
</template>

<script>
export default {
  name: "AlbumCard",
  props: {
    album: Object,
  },
};
</script>

<style scoped lang="scss">
#album-card {
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
</style>
