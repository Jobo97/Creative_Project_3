<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('Ohio')" href="#" class="pure-menu-link">Ohio</a></li>
      <li class="pure-menu-item"><a @click="select('California')" href="#" class="pure-menu-link">California</a></li>
      <li class="pure-menu-item"><a @click="select('Mississippi')" href="#" class="pure-menu-link">Mississippi</a></li>
      <li class="pure-menu-item"><a @click="select('South Carolina')" href="#" class="pure-menu-link">South Carolina</a></li>
      <li class="pure-menu-item"><a @click="select('Texas')" href="#" class="pure-menu-link">Texas</a></li>
      <li class="pure-menu-item"><a @click="select('Oklahoma')" href="#" class="pure-menu-link">Oklahoma</a></li>
      <li class="pure-menu-item"><a @click="select('Hawaii')" href="#" class="pure-menu-link">Hawaii</a></li>
      <li class="pure-menu-item"><a @click="select('Florida')" href="#" class="pure-menu-link">Florida</a></li>
    </ul>
  </div>
  <PlayersList :playersInfo="playersInfo" />
</div>
</template>

<script>
import PlayersList from "../components/PlayersList.vue"
export default {
  name: 'Browse',
  components: {
    PlayersList
  },
  data() {
    return {
      country: '',
    }
  },
  computed: {
    playersInfo() {
      return this.$root.$data.playersInfo.filter(product => product.country === this.country);
    }
  },
  methods: {
    select(country) {
      this.country = country;
    }
  }
}
</script>