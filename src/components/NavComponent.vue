<script setup lang="ts"></script>

<template>
  <nav>
    <ul class="nav-links">
      <li><a href="#home">Accueil</a></li>
      <li><a href="#about">A propos</a></li>
      <li><a href="#projects">Projets</a></li>
      <li><a href="#skills">Compétences</a></li>
      <li><a href="#experiences">Expériences</a></li>
      <li><a href="#formations">Formations</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
</template>

<style scoped lang="scss">
nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;

  ul {
    display: flex;
    justify-content: center;
    list-style: none;
    gap: 3rem;
    background-color: rgba(52, 78, 65, 0.2);
    backdrop-filter: blur(30px);
    padding: 1.5rem;

    li {
      margin: 0 1rem;

      a {
        text-decoration: none;
        color: $green-700;
        font-size: 1.2rem;
        transition: color 0.3s ease;

        &:hover {
          color: white;
          text-decoration: underline;
        }
      }
    }
  }
}

@media screen and (max-width: 768px) {
  nav {
    display: none;
  }
}
</style>
