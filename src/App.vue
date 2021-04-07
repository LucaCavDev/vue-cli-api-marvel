<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> 
      &nbsp;
      <img 
      alt="Sheld logo" 
      src="./assets/shield.svg" 
      style="height: 30px;" 
      /> 
      &nbsp;
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #111;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: grey;

    &.router-link-exact-active {
      color: lightgrey;
    }
  }
}
</style>
