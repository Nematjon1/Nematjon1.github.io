<template>
  <div class="pt-4 contact">
    <div class="contact__info">
      <p>
        Check out my
        <a href="https://github.com/Nematjon1">Github Account</a>
        for reference.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Contacts"
};
</script>

<style lang="scss">
.contact {
  font-size: 1.1rem;
}

.contact__info {
  margin: 6rem auto;
  width: 100%;
  max-width: 600px;
  background-color: hsl(200, 60%, 94%);
  border: 2px solid hsl(200, 60%, 70%);
  border-radius: 0.4rem;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.2);
  padding: 1rem 1.5rem;
}

.contact__info a:link,
.contact__info a:visited {
  text-decoration: none;
  color: hsl(200, 40%, 40%);
  display: inline-block;
  padding: 0 0.3rem;
}
</style>
