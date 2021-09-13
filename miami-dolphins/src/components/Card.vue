<template>
  <v-row justify="center">
    <v-card
      v-for="(player, i) in dolphins"
      class="mx-auto my-12"
      max-width="374"
      :key="i"
    >
      <v-img height="250" :src="require(`@/${player.src}`)"></v-img>

      <v-card-title>{{ player.name }}</v-card-title>

      <v-card-text>
        <div>Position: {{ player.position }}</div>
      </v-card-text>

      <v-divider class="mx-4"></v-divider>

      <v-card-actions>
        <v-btn color="deep-purple lighten-2" text @click="handleClick">
          Click Me
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-row>
</template>

<script>
export default {
  name: "Card",

  data: () => ({
    dolphins: [
      {
        id: 1,
        name: "Tua Tagovailoa",
        src: "assets/logo.png",
        position: "QB",
      },
      {
        id: 2,
        name: "DeVante Parker",
        src: "assets/logo.png",
        position: "WR",
      },
      {
        id: 3,
        name: "Preston Williams",
        src: "assets/logo.png",
        position: "WR",
      },
    ],
  }),
  methods: {
    handleClick() {
      alert("Coming soon!");
    },
  },
};
</script>
