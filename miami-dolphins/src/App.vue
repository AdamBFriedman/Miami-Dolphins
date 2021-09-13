<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Miami Dolphins Logo"
          class="shrink mr-2"
          contain
          src="./assets/logo.png"
          transition="scale-transition"
          width="70"
        />
      </div>

      <v-spacer></v-spacer>
    </v-app-bar>

    <v-main>
      <Card />
    </v-main>
  </v-app>
</template>

<script>
import Card from "./components/Card";

export default {
  name: "App",

  components: {
    Card,
  },

  data: () => ({
    logo: "./assets/logo.png",
  }),
};
</script>
