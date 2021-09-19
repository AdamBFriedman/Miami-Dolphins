<template>
  <v-row justify="center">
    <v-card class="card my-12" max-width="374" @click="handleClick">
      <v-img height="250" width="250" :src="require(`@/${src}`)"></v-img>

      <v-card-title
        >{{ firstNameCapitalized }} {{ lastNameCapitalized }}</v-card-title
      >

      <v-card-text class="card-text">
        <strong>Position:</strong> {{ position }}
      </v-card-text>
      <v-card-text class="card-text">
        <strong>Number:</strong> {{ number }}
      </v-card-text>
    </v-card>
  </v-row>
</template>

<style scoped>
.card {
  box-shadow: 8px 8px 12px #fc4c02 !important;
  cursor: pointer;
}
.card-text {
  padding: 0 0.5em 0.5em !important;
}
</style>

<script>
export default {
  name: "Card",
  props: {
    firstName: String,
    lastName: String,
    depth: Number,
    position: String,
    src: String,
    number: Number,
  },
  data: () => ({}),
  methods: {
    handleClick() {
      alert("Coming soon!");
    },
    capitalizeString(str) {
      return str.replace(/\w/, (c) => c.toUpperCase());
    },
  },
  computed: {
    firstNameCapitalized: function() {
      return this.capitalizeString(this.firstName);
    },
    lastNameCapitalized: function() {
      return this.capitalizeString(this.lastName);
    },
  },
};
</script>
