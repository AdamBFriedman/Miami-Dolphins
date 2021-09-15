<template>
  <v-container class="menu">
    <v-select
      v-model="selected"
      :items="items"
      label="Filter by..."
      solo
      @change="handleChange"
      color="#fc4c02"
    ></v-select>
  </v-container>
</template>

<style scoped>
.menu {
  width: 20%;
}
@media (max-width: 600px) {
  .menu {
    width: 90%;
  }
}
</style>

<script>
export default {
  name: "Menu",
  data: () => ({
    selected: "",
    items: ["First Team", "Second Team", "Full Squad"],
  }),
  methods: {
    handleChange() {
      this.$emit("filtered", this.selected);
    },
  },
};
</script>
