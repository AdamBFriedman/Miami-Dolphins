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

    <v-main class="d-flex">
      <v-row>
        <Card
          v-for="(player, i) in firstTeamQB"
          :key="i"
          :playerName="player.playerName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row>
        <Card
          v-for="(player, i) in firstTeamRB"
          :key="i"
          :playerName="player.playerName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row>
        <Card
          v-for="(player, i) in firstTeamTE"
          :key="i"
          :playerName="player.playerName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row>
        <Card
          v-for="(player, i) in firstTeamWR"
          :key="i"
          :playerName="player.playerName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row>
        <Card
          v-for="(player, i) in firstTeamOLine"
          :key="i"
          :playerName="player.playerName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
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
  computed: {
    firstTeam: function() {
      return this.dolphins.filter((player) => {
        return player.depth === 1;
      });
    },
    secondTeam: function() {
      return this.dolphins.filter((player) => {
        return player.depth === 2;
      });
    },
    firstTeamQB: function() {
      return this.firstTeam.filter((player) => {
        return player.position === "QB";
      });
    },
    firstTeamRB: function() {
      return this.firstTeam.filter((player) => {
        return player.position === "RB";
      });
    },
    firstTeamTE: function() {
      return this.firstTeam.filter((player) => {
        return player.position === "TE";
      });
    },
    firstTeamWR: function() {
      return this.firstTeam.filter((player) => {
        return player.position === "WR";
      });
    },
    firstTeamOLine: function() {
      return this.firstTeam.filter((player) => {
        return (
          player.position === "LT" ||
          player.position === "LG" ||
          player.position === "C" ||
          player.position === "RT" ||
          player.position === "RG"
        );
      });
    },
  },
};
</script>
