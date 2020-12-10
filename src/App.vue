<template>
  <div id="app">
    <div id="nav">
      <div class="logo">
        <span>Nematjon Abdulloev</span>
      </div>

      <div class="nav__links">
        <router-link to="/">Home</router-link> |
        <router-link to="/projects">Projects</router-link> |
        <router-link to="/contacts">Contacts</router-link> |
        <router-link to="/about">About</router-link>
      </div>
    </div>
    <router-view />
  </div>
</template>

<script>
export default {
  name: "App"
};
</script>

<style src="@/scss/styles.scss" lang="scss"></style>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
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
