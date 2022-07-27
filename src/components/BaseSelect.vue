<template>
  <select v-model="selected" class="form-select" @change="emitSelect" aria-label="Default select example">
    <option value="" selected>-- --</option>
    <option v-for="(element, i) in array" :key="i" :value="element">{{ element }}</option>
  </select>
</template>

<script>
export default {
  name: "BaseHeader",
  props: {
    array: Array,
  },
  data() {
    return {
      selected: "",
    };
  },
  methods: {
    emitSelect() {
      this.$emit("selected", this.selected);
    },
  },
};
</script>

<style lang="scss" scoped>
select {
  width: 200px;
  cursor: pointer;
}
</style>
