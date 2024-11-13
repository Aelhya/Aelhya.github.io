<script setup lang="ts">
function scrollDown() {
  window.scrollTo({
    top: window.innerHeight,
    behavior: "smooth",
  });
}
</script>

<template>
  <section id="hero">
    <div class="hero-content">
      <p>~ Cheffe de Projet | Product Owner | Développeuse Front-End ~</p>
      <h1>Adélaïde LOUIS</h1>
      <p class="description">
        Passionnée de web et de design | Accro aux challenges
      </p>
    </div>
    <div class="scroll-indicator" @click="scrollDown"></div>
  </section>
</template>

<style scoped lang="scss">
#hero {
  position: relative;
  background-image: url("../../assets/img/hero-background.jpg");
  background-size: cover;
  background-position: center;
  height: 90vh;
  display: flex;
  align-items: center;
  justify-content: center;
  color: $green-700;

  h1 {
    font-weight: 700;
  }

  p {
    font-weight: 400;
  }

  .hero-content {
    text-align: center;
  }

  h1 {
    font-size: 4rem;
  }

  p {
    font-size: 1.5rem;
    margin-top: 10px;
    color: $green-300;
  }
}

.scroll-indicator {
  display: inline-block;
  width: 70px;
  height: 70px;
  border-radius: 50%;
  position: absolute;
  bottom: 8rem;
  left: 50%;
  transform: translateX(-50%);
  cursor: pointer;
  transition: background-color 0.3s ease;
  background-color: $green-700;

  &::before {
    content: "";
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 0;
    height: 0;
    border-left: 10px solid transparent;
    border-right: 10px solid transparent;
    border-top: 10px solid $white;
    animation: scroll-down 2s infinite;
  }

  &:hover {
    background-color: darken($green-700, 10%);
  }
}

.description {
  font-style: italic;
}

@keyframes scroll-down {
  0% {
    transform: translate(-50%, -50%) translateY(0);
  }
  50% {
    transform: translate(-50%, -50%) translateY(10px);
  }
  100% {
    transform: translate(-50%, -50%) translateY(0);
  }
}

@media screen and (max-width: 768px) {
  .scroll-indicator {
    width: 50px;
    height: 50px;
    top: 90%;

    &::before {
      top: 60%;
    }
  }
}
</style>
