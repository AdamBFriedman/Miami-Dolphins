<template>
  <v-row justify="center">
    <v-card class="card my-12" max-width="374" @click="handleClick">
      <v-img height="250" width="250" :src="require(`@/${src}`)"></v-img>

      <v-card-title>{{ playerName }}</v-card-title>

      <v-card-text> <strong>Position:</strong> {{ position }} </v-card-text>
    </v-card>
  </v-row>
</template>

<style scoped>
.card {
  box-shadow: 8px 8px 12px #fc4c02 !important;
  cursor: pointer;
}
</style>

<script>
export default {
  name: "Card",
  props: {
    playerName: String,
    depth: Number,
    position: String,
    src: String,
  },
  data: () => ({}),
  methods: {
    handleClick() {
      alert("Coming soon!");
    },
  },
};
</script>
