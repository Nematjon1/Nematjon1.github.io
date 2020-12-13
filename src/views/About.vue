<template>
  <div class="about">
    <h4 class="about__title">Nematjon Abdulloev</h4>
    <p class="about__description">
      Web developer since 2017. Mostly interested in createing web application
      and web-sites. Uses data structures, algorithms, popular design patterns,
      and programming paradigms. Solid foundation on Web APIs and RESTful
      architecture. Follows best practices and popular methodologies. Has pretty
      good communication skills and positive person.
    </p>
  </div>
</template>

<style lang="scss">
.about {
  border: 2px solid hsl(200, 70%, 60%);
  background-color: hsl(200, 60%, 93%);
  max-width: 600px;
  margin: 4rem auto;
  border-radius: 0.5rem;
  padding: 0.4rem 0.6rem;
}

.about__title {
  text-align: center;
  font-size: 1.5rem;
  margin: 0.6rem 0;
  color: hsl(200, 40%, 50%);
}

.about__description {
  line-height: 1.3;
  letter-spacing: 1px;
  text-indent: 4px;
}
</style>
