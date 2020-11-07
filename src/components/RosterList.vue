<template>
  <div class="wrapper">
    <div class="playersInfo">
      <h2 class="playerInfo" v-if="isEmpty"><em>No players on roster!</em></h2>
      <div class="playerInfo" v-for="playerInfo in playersInfo" :key="playerInfo.id">
        <div class="info">
          <h1>{{ playerInfo.name }}</h1>
          <p>{{ playerInfo.country }}</p>
        </div>
        <div class="image">
          <img :src="'/images/players/' + playerInfo.image" />
        </div>
        <div class="price">
          <h2>{{ playerInfo.price }}</h2>
          <button @click="removeFromRoster(playerInfo)" class="auto">
            Remove Player
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.playersInfo {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.playerInfo {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}

.playerInfo img {
  border: 2px solid #333;
  height: 250px;
  width: 200px;
  object-fit: cover;
}

.playerInfo .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #f2921d;
  color: #000;
  padding: 10px 30px;
  height: 80px;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}

.price {
  display: flex;
}

button {
  height: 50px;
  background: #000;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>

<script>
export default {
  name: "CartList",
  props: {
    playersInfo: Array
  },
  computed: {
    isEmpty() {
      if (this.$root.$data.players.length === 0) {
        return true;
      } else return false;
    }
  },
  methods: {
    removeFromRoster(playerInfo) {
      let index = this.$root.$data.players.indexOf(playerInfo);
      if (index > -1) {
        this.$root.$data.players.splice(index, 1);
      }
    }
  }
};
</script>