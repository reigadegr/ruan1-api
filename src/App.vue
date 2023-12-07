<template>
  <nav>
   | <router-link to="/">Home原生api</router-link> |
    <router-link to="/about">About组合api</router-link> |
    <router-link to="/setup">入口setup</router-link> |
    <router-link to="/comapi">c常用api</router-link> |
    <router-link to="/watch">c侦听器</router-link> |
  </nav>
  <router-view/>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
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
