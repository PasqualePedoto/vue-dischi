<template>
  <section class="container">
    <header>
      <figure class="m-0"><img class="img-fluid" src="../assets/image/logo.svg" alt="spotify-logo" /></figure>
    </header>
  </section>
</template>

<script>
export default {
  name: "BaseHeader",
};
</script>

<style scoped lang="scss">
header {
  background-color: #2e3a46;
  padding: 10px;

  figure {
    width: 150px;
  }
}
</style>
