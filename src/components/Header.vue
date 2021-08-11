<template>
  <nav class="navbar">
    <router-link to="/" class="navbar__logo"
      ><span>Front End Developer</span></router-link
    >
    <span class="navbar__author">Nematjon Abdulloev</span>

    <ul class="navbar__links">
      <router-link to="/" exact>Home</router-link>
      <router-link to="/projects">Projects</router-link>
      <router-link to="/contacts">Contacts</router-link>
      <router-link to="/about">About</router-link>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style lang="scss">
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  height: 7vh;
  min-width: 100vw;
  max-width: 100vw;
  border-bottom: 2px solid hsl(200, 30%, 50%);
  display: flex;
  font-size: 0.7rem;
  justify-content: space-between;
  background-image: linear-gradient(
    to bottom,
    hsl(200, 60%, 90%),
    hsl(200, 60%, 85%)
  );
}

.navbar__links,
.navbar__author,
.navbar__logo {
  display: flex;
  align-items: center;
  margin: 0;
  padding: 0 0.5rem;
}

.navbar__logo:link,
.navbar__logo:visited {
  color: hsl(200, 30%, 50%);
  text-decoration: none;
  transition: 0.2s ease-out;
}

.navbar__logo:active,
.navbar__logo:hover {
  transform: translate(-1px, -3px) scale(1.02);
}

.navbar__author {
  flex: 1;
  justify-content: center;
  font-size: 0.5rem;
}

.navbar__links {
  padding-right: 1.2rem;
}
.navbar__links > a {
  text-decoration: none;
  color: hsl(200, 35%, 60%);
}

.navbar__links .router-link-active {
  text-decoration: none;
  color: hsl(200, 30%, 40%);
}
.navbar__links > a:not(:last-of-type) {
  margin-right: 0.7rem;
}

@media (min-width: 500px) {
  .navbar {
    height: 8vh;
    font-size: 0.9rem;
  }

  .navbar__links,
  .navbar__author,
  .navbar__logo {
    padding: 0 1.2rem;
  }

  .navbar__author {
    font-size: 0.9rem;
  }
  .navbar__links {
    padding-right: 1.2rem;
  }
  .navbar__links > a:not(:last-of-type) {
    margin-right: 0.7rem;
  }
}
</style>
