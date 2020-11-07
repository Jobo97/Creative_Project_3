<template>
  <div>
    <h1 class="wrapper">Team Roster:</h1>
    <RosterList :playersInfo="playersInfo" />
  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>

<script>
import RosterList from "../components/RosterList.vue";
export default {
  name: "Roster",
  components: {
    RosterList
  },
  computed: {
    playersInfo() {
      return this.$root.$data.players;
    }
  }
};
</script>