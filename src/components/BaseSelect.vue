<template>
  <select class="form-select" aria-label="Default select example">
    <option>-- --</option>
    <option value="1" selected>One</option>
    <option value="2">Two</option>
    <option value="3">Three</option>
  </select>
</template>

<script>
export default {
  name: "BaseHeader",
};
</script>

<style lang="scss" scoped>
select {
  width: 200px;
  cursor: pointer;
}
</style>
