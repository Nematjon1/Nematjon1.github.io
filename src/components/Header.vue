<template>
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
</template>

<script>
export default {
  name: "Header"
};
</script>

<style></style>
