<template>
  <v-row justify="center">
    <v-card
      v-for="(player, i) in dolphins"
      class="mx-auto my-12"
      max-width="374"
      :key="i"
    >
      <v-img height="250" width="250" :src="require(`@/${player.src}`)"></v-img>

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
        src: "assets/tua_tagovailoa.png",
        position: "QB",
        depth: 1,
      },
      {
        id: 2,
        name: "DeVante Parker",
        src: "assets/devante_parker.png",
        position: "WR",
        depth: 1,
      },
      {
        id: 3,
        name: "Jaylen Waddle",
        src: "assets/jaylen_waddle.png",
        position: "WR",
        depth: 1,
      },
      {
        id: 4,
        name: "Jakeem Grant Sr",
        src: "assets/jakeem_grant.png",
        position: "WR",
        depth: 1,
      },
      {
        id: 5,
        name: "Myles Gaskin",
        src: "assets/myles_gaskin.png",
        position: "RB",
        depth: 1,
      },
      {
        id: 6,
        name: "Mike Gesicki",
        src: "assets/mike_gesicki.png",
        position: "TE",
        depth: 1,
      },
      {
        id: 7,
        name: "Austin Jackson",
        src: "assets/austin_jackson.png",
        position: "LT",
        depth: 1,
      },
      {
        id: 8,
        name: "Solomon Kindley",
        src: "assets/solomon_kindley.png",
        position: "LG",
        depth: 1,
      },
      {
        id: 9,
        name: "Michael Deiter",
        src: "assets/michael_deiter.png",
        position: "C",
        depth: 1,
      },
      {
        id: 10,
        name: "Robert Hunt",
        src: "assets/robert_hunt.png",
        position: "RG",
        depth: 1,
      },
      {
        id: 11,
        name: "Jesse Davis",
        src: "assets/jesse_davis.png",
        position: "RT",
        depth: 1,
      },
      {
        id: 12,
        name: "Jacoby Brissett",
        src: "assets/jacoby_brissett.png",
        position: "QB",
        depth: 2,
      },
      {
        id: 13,
        name: "Preston Williams",
        src: "assets/preston_williams.png",
        position: "WR",
        depth: 2,
      },
      {
        id: 14,
        name: "Albert Wilson",
        src: "assets/albert_wilson.png",
        position: "WR",
        depth: 2,
      },
      {
        id: 15,
        name: "Mack Hollins",
        src: "assets/mack_hollins.png",
        position: "WR",
        depth: 2,
      },
      {
        id: 16,
        name: "Malcolm Brown",
        src: "assets/malcolm_brown.png",
        position: "RB",
        depth: 2,
      },
      {
        id: 17,
        name: "Adam Shaheen",
        src: "assets/adam_shaheen.png",
        position: "TE",
        depth: 2,
      },
      {
        id: 18,
        name: "Greg Little",
        src: "assets/greg_little.png",
        position: "LT",
        depth: 2,
      },
      {
        id: 19,
        name: "Robert Jones",
        src: "assets/robert_jones.png",
        position: "LG",
        depth: 2,
      },
      {
        id: 20,
        name: "Greg Mancz",
        src: "assets/greg_mancz.png",
        position: "C",
        depth: 2,
      },
      {
        id: 21,
        name: "Robert Jones",
        src: "assets/robert_jones.png",
        position: "RG",
        depth: 2,
      },
      {
        id: 22,
        name: "Liam Eichenberg",
        src: "assets/liam_eichenberg.png",
        position: "RT",
        depth: 2,
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
