<template>
  <v-app class="app">
    <v-app-bar app class="appbar">
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
      <Menu @filtered="handleChange" />

      <v-row class="row" v-if="firstTeamFilter">
        <Card
          v-for="(player, i) in firstTeamQB"
          :key="i"
          :firstName="player.firstName"
          :lastName="player.lastName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="secondTeamFilter">
        <Card
          v-for="(player, i) in secondTeamQB"
          :key="i"
          :firstName="player.firstName"
          :lastName="player.lastName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="firstTeamFilter">
        <Card
          v-for="(player, i) in firstTeamRB"
          :key="i"
          :firstName="player.firstName"
          :lastName="player.lastName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="secondTeamFilter">
        <Card
          v-for="(player, i) in secondTeamRB"
          :key="i"
          :firstName="player.firstName"
          :lastName="player.lastName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="firstTeamFilter">
        <Card
          v-for="(player, i) in firstTeamTE"
          :key="i"
          :firstName="player.firstName"
          :lastName="player.lastName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="secondTeamFilter">
        <Card
          v-for="(player, i) in secondTeamTE"
          :key="i"
          :firstName="player.firstName"
          :lastName="player.lastName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="firstTeamFilter">
        <Card
          v-for="(player, i) in firstTeamWR"
          :key="i"
          :firstName="player.firstName"
          :lastName="player.lastName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="secondTeamFilter">
        <Card
          v-for="(player, i) in secondTeamWR"
          :key="i"
          :firstName="player.firstName"
          :lastName="player.lastName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="firstTeamFilter">
        <Card
          v-for="(player, i) in firstTeamOLine"
          :key="i"
          :firstName="player.firstName"
          :lastName="player.lastName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="firstTeamFilter">
        <Card
          v-for="(player, i) in firstTeamSpecialTeam"
          :key="i"
          :firstName="player.firstName"
          :lastName="player.lastName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="secondTeamFilter">
        <Card
          v-for="(player, i) in secondTeamOLine"
          :key="i"
          :firstName="player.firstName"
          :lastName="player.lastName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="fullSquadFilter">
        <Card
          v-for="(player, i) in fullSquad"
          :key="i"
          :firstName="player.firstName"
          :lastName="player.lastName"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
    </v-main>
  </v-app>
</template>

<style scoped>
:root {
  --aqua: #008e97;
  --orange: #fc4c02;
}
.app {
  background: #008e97 !important;
}
.appbar {
  background: #fc4c02 !important;
}
.row {
  margin: 0;
}
</style>

<script>
import Card from "./components/Card";
import Menu from "./components/Menu";
import offense from "./miamiDolphinsOffense.js";
import defense from "./miamiDolphinsDefense.js";

export default {
  name: "App",

  components: {
    Card,
    Menu,
  },
  data: () => ({
    offense,
    defense,
    filteredOption: "First Team",
  }),
  computed: {
    firstTeamFilter: function() {
      return this.filteredOption === "First Team";
    },
    secondTeamFilter: function() {
      return this.filteredOption === "Second Team";
    },
    fullSquadFilter: function() {
      return this.filteredOption === "Full Squad";
    },
    firstTeam: function() {
      return this.offense.filter((player) => {
        return player.depth === 1;
      });
    },
    secondTeam: function() {
      return this.offense.filter((player) => {
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
    firstTeamSpecialTeam: function() {
      return this.firstTeam.filter((player) => {
        return player.position === "K" || player.position === "P";
      });
    },
    secondTeamQB: function() {
      return this.secondTeam.filter((player) => {
        return player.position === "QB";
      });
    },
    secondTeamRB: function() {
      return this.secondTeam.filter((player) => {
        return player.position === "RB";
      });
    },
    secondTeamTE: function() {
      return this.secondTeam.filter((player) => {
        return player.position === "TE";
      });
    },
    secondTeamWR: function() {
      return this.secondTeam.filter((player) => {
        return player.position === "WR";
      });
    },
    secondTeamOLine: function() {
      return this.secondTeam.filter((player) => {
        return (
          player.position === "LT" ||
          player.position === "LG" ||
          player.position === "C" ||
          player.position === "RT" ||
          player.position === "RG"
        );
      });
    },
    fullSquad: function() {
      const fullSquad = this.offense.concat(this.defense);
      return fullSquad;
    },
  },
  methods: {
    handleChange(value) {
      this.filteredOption = value;
    },
  },
};
</script>
