<template>
  <div class="pt-4 home">
    <div class="home__hero">
      <div class="motion"></div>

      <div class="main">
        <h1 class="main__title">Welcome, dear guest!</h1>
        <h3 class="main__subtitle">
          My name is Nematjon Abdulloev, I am a web developer.
        </h3>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  components: {}
};
</script>

<style lang="scss">
.home {
  display: flex;
  align-items: center;
  padding: 4rem 1.3rem;
}

.home__hero {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 280px;
  max-width: 600px;
  margin: 0 auto;
  width: 100%;
}
.motion {
  border: 2px solid hsl(190, 50%, 80%);
  box-shadow: 0px 5px 7px rgba(0, 0, 0, 0.3);
  flex: 40%;
  height: 100%;
  width: 100%;
  background-image: linear-gradient(
    to bottom left,
    hsl(200, 40%, 95%),
    hsl(199, 50%, 95%)
  );
}

.main {
  position: absolute;
  flex: 60%;
  padding: 0 0.5rem;
}

.main__title {
  letter-spacing: 2px;
  font-size: 2rem;
  text-transform: capitalize;
}
</style>
