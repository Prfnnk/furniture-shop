<template>
  <div class="app" id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link>
    </div> -->
    <router-view />
  </div>
</template>

<style>
* {
  box-sizing: border-box;
}
.app {
  font-family: 'Gilroy', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  max-width: 1440px;
  width: 100%;
  margin: 0 auto;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
}
body {
  margin: 0;
}
</style>
