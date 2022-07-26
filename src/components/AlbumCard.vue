<template>
  <section id="album-card">
    <figure class="m-0">
      <img class="img-fluid h-100 w-100" :src="Album.poster" :alt="Album.title" />
    </figure>
    <div id="caption" class="align-content-between text-center">
      <h4 class="m-0 mt-3 mb-5 text-white">{{ Album.title }}</h4>
      <div class="mt-3">
        <p class="m-0 text-gray">{{ Album.author }}</p>
        <p class="m-0 text-gray">{{ Album.year }}</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AlbumCard",
  props: {
    Album: Object,
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
