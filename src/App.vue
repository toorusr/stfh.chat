<template>
  <div id="app">
    <div class="text-xs text-right opacity-25" id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-link to="/imprint">Imprint</router-link> |
      <router-link to="/privacy">Privacy</router-link> |
      <router-link to="/contact">Contact</router-link> |
      <router-link to="/creator">Maker</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: 'Open Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
