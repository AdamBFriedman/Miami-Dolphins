<template>
  <v-row justify="center">
    <v-card class="mx-auto my-12" max-width="374">
      <v-img height="250" width="250" :src="require(`@/${src}`)"></v-img>

      <v-card-title>{{ playerName }}</v-card-title>

      <v-card-text>
        <div>Position: {{ position }}</div>
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
