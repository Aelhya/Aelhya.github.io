<script setup lang="ts"></script>

<template>
  <section id="not-found">
    <div class="hero-content">
      <h1>Page non trouvée</h1>
      <p class="description">
        <router-link to="/">Retour à l'accueil</router-link>
      </p>
    </div>
  </section>
</template>

<style scoped lang="scss">
#not-found {
  position: relative;
  background-image: url("src/assets/img/hero-background.jpg");
  background-size: cover;
  background-position: center;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  color: $green-700;

  h1 {
    font-weight: 700;
  }

  p {
    font-weight: 400;
    text-align: center;
  }

  a {
    color: $green-700;

    &:hover {
      color: $green-500;
    }
  }
}
</style>
