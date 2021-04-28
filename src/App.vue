<template>
  <div id="app">
    <nav class="app-nav">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </nav>
    <router-view></router-view>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
body {
  margin: 0;
  font-family: sans-serif;
}
.app-nav {
  display: flex;
  align-items: center;
  padding: 10px;
  box-sizing: border-box;
  height: 40px;
  background: lightpink;
  
  a {
    font-size: 16px;
    font-family: sans-serif;
    margin: 0 10px;
    text-decoration: none;
  }
}
</style>
