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
          :playerName="player.name"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="secondTeamFilter">
        <Card
          v-for="(player, i) in secondTeamQB"
          :key="i"
          :playerName="player.name"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="firstTeamFilter">
        <Card
          v-for="(player, i) in firstTeamRB"
          :key="i"
          :playerName="player.name"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="secondTeamFilter">
        <Card
          v-for="(player, i) in secondTeamRB"
          :key="i"
          :playerName="player.name"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="firstTeamFilter">
        <Card
          v-for="(player, i) in firstTeamTE"
          :key="i"
          :playerName="player.name"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="secondTeamFilter">
        <Card
          v-for="(player, i) in secondTeamTE"
          :key="i"
          :playerName="player.name"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="firstTeamFilter">
        <Card
          v-for="(player, i) in firstTeamWR"
          :key="i"
          :playerName="player.name"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="secondTeamFilter">
        <Card
          v-for="(player, i) in secondTeamWR"
          :key="i"
          :playerName="player.name"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="firstTeamFilter">
        <Card
          v-for="(player, i) in firstTeamOLine"
          :key="i"
          :playerName="player.name"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="firstTeamFilter">
        <Card
          v-for="(player, i) in firstTeamSpecialTeam"
          :key="i"
          :playerName="player.name"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="secondTeamFilter">
        <Card
          v-for="(player, i) in secondTeamOLine"
          :key="i"
          :playerName="player.name"
          :position="player.position"
          :src="player.src"
        />
      </v-row>
      <v-row class="row" v-if="fullSquadFilter">
        <Card
          v-for="(player, i) in fullSquad"
          :key="i"
          :playerName="player.name"
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

export default {
  name: "App",

  components: {
    Card,
    Menu,
  },
  data: () => ({
    logo: "./assets/logo.png",
    offense: [
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
        name: "Jason Sanders",
        src: "assets/jason_sanders.png",
        position: "K",
        depth: 1,
      },
      {
        id: 13,
        name: "Michael Palardy",
        src: "assets/michael_palardy.png",
        position: "P",
        depth: 1,
      },
      {
        id: 14,
        name: "Jacoby Brissett",
        src: "assets/jacoby_brissett.png",
        position: "QB",
        depth: 2,
      },
      {
        id: 15,
        name: "Preston Williams",
        src: "assets/preston_williams.png",
        position: "WR",
        depth: 2,
      },
      {
        id: 16,
        name: "Albert Wilson",
        src: "assets/albert_wilson.png",
        position: "WR",
        depth: 2,
      },
      {
        id: 17,
        name: "Mack Hollins",
        src: "assets/mack_hollins.png",
        position: "WR",
        depth: 2,
      },
      {
        id: 18,
        name: "Malcolm Brown",
        src: "assets/malcolm_brown.png",
        position: "RB",
        depth: 2,
      },
      {
        id: 19,
        name: "Adam Shaheen",
        src: "assets/adam_shaheen.png",
        position: "TE",
        depth: 2,
      },
      {
        id: 20,
        name: "Greg Little",
        src: "assets/greg_little.png",
        position: "LT",
        depth: 2,
      },
      {
        id: 21,
        name: "Robert Jones",
        src: "assets/robert_jones.png",
        position: "LG",
        depth: 2,
      },
      {
        id: 22,
        name: "Greg Mancz",
        src: "assets/greg_mancz.png",
        position: "C",
        depth: 2,
      },
      {
        id: 23,
        name: "Robert Jones",
        src: "assets/robert_jones.png",
        position: "RG",
        depth: 2,
      },
      {
        id: 24,
        name: "Liam Eichenberg",
        src: "assets/liam_eichenberg.png",
        position: "RT",
        depth: 2,
      },
    ],
    defense: [
      {
        id: 1,
        name: "Emmanuel Ogbah",
        src: "assets/emmanuel_ogbah.png",
        position: "DE",
        depth: 1,
      },
      {
        id: 2,
        name: "Raekwon Davis",
        src: "assets/raekwon_davis.png",
        position: "NT",
        depth: 1,
      },
      {
        id: 3,
        name: "Christian Wilkins",
        src: "assets/christian_wilkins.png",
        position: "DE",
        depth: 1,
      },
      {
        id: 4,
        name: "Jerome Baker",
        src: "assets/jerome_baker.png",
        position: "LB",
        depth: 1,
      },
      {
        id: 5,
        name: "Elandon Roberts",
        src: "assets/elandon_roberts.png",
        position: "LB",
        depth: 1,
      },
      {
        id: 6,
        name: "Andrew Van Ginkel",
        src: "assets/andrew_ginkel.png",
        position: "LB",
        depth: 1,
      },
      {
        id: 7,
        name: "Justin Coleman",
        src: "assets/justin_coleman.png",
        position: "CB",
        depth: 1,
      },
      {
        id: 8,
        name: "Byron Jones",
        src: "assets/byron_jones.png",
        position: "CB",
        depth: 1,
      },
      {
        id: 9,
        name: "Xavien Howard",
        src: "assets/xavien_howard.png",
        position: "CB",
        depth: 1,
      },
      {
        id: 10,
        name: "Jason McCourty",
        src: "assets/jason_mcCourty.png",
        position: "S",
        depth: 1,
      },
      {
        id: 11,
        name: "Eric Rowe",
        src: "assets/eric_rowe.png",
        position: "S",
        depth: 1,
      },
      {
        id: 12,
        name: "Adam Butler",
        src: "assets/adam_butler.png",
        position: "DE",
        depth: 2,
      },
      {
        id: 13,
        name: "John Jenkins",
        src: "assets/john_jenkins.png",
        position: "NT",
        depth: 2,
      },
      {
        id: 14,
        name: "Zach Sieler",
        src: "assets/zach_sieler.png",
        position: "DE",
        depth: 2,
      },
      {
        id: 15,
        name: "Duke Riley",
        src: "assets/duke_riley.png",
        position: "LB",
        depth: 2,
      },
      {
        id: 16,
        name: "Sam Eguavoen",
        src: "assets/sam_eguavoen.png",
        position: "LB",
        depth: 2,
      },
      {
        id: 17,
        name: "Brennan Scarlett",
        src: "assets/brennan_scarlett.png",
        position: "LB",
        depth: 2,
      },
      {
        id: 18,
        name: "Elijah Campbell",
        src: "assets/elijah_campbell.png",
        position: "CB",
        depth: 2,
      },
      {
        id: 19,
        name: "Noah Igbinoghene",
        src: "assets/noah_igbinoghene.png",
        position: "CB",
        depth: 2,
      },
      {
        id: 20,
        name: "Nik Needham",
        src: "assets/nik_needham.png",
        position: "CB",
        depth: 2,
      },
      {
        id: 21,
        name: "Jevon Holland",
        src: "assets/jevon_holland.png",
        position: "S",
        depth: 2,
      },
      {
        id: 22,
        name: "Brandon Jones",
        src: "assets/brandon_jones.png",
        position: "S",
        depth: 2,
      },
    ],
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
