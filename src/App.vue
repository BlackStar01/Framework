<template>
  <div id="nav">
    <router-link to="/">Home</router-link>
    <!-- <router-link to="/about">About</router-link> -->
  </div>
  <router-view/>
</template>

<style lang="scss">
@import "../public/_theme.scss";
@import url('https://fonts.googleapis.com/css2?family=Outfit&display=swap');

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
#app {
  font-family: 'Outfit', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
