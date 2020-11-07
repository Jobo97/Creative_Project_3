<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <img src="/images/logo.png">
      </router-link>
    </div>
    <div id="side">
      <router-link to="/browse">
        <div class="menu-item browse">
          <img src="/images/globe.png">
          <p>Browse</p>
        </div>
      </router-link>
      <router-link to="/roster">
        <div class="menu-item">
          <img src="/images/team.png" />
          <p>{{ rosterSize }} players</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
  <div id="footer">
    <footer>
    <p>Github Link<br>
      <a href="https://github.com/Jobo97/Creative_Project_3.git" target="_blank">See the code behind this page here!</a><br> Created By: <br> Ben Millett <br> Michael Skonnard</p>
    </footer>
  </div>
</div>
</template>

<script>
export default {
  name: "App",
  computed: {
    rosterSize() {
      return this.$root.$data.players.length;
    }
  }
};
</script>

<style>
#footer {
  text-align: center;
  padding: 3px;
}
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;

}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#menu a {
  color: #B84901;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}
</style>
