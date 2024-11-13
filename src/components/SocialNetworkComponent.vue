<script setup>
import { Icon } from "@iconify/vue";
</script>

<template>
  <div>
    <a
      class="social-link rounded-circle text-white"
      href="https://www.linkedin.com/in/adélaïde-louis/"
      target="_blank"
    >
      <Icon icon="jam:linkedin-square" class="icon" />
    </a>

    <a
      class="social-link rounded-circle text-white"
      href="https://github.com/Aelhya"
      target="_blank"
    >
      <Icon icon="jam:github-square" class="icon" />
    </a>
  </div>
</template>

<style scoped lang="scss">
div {
  margin: 0;
  list-style: none;
  display: flex;
  gap: 1rem;
  justify-content: center;

  .icon {
    font-size: 2rem;
    color: $white;
    transition: color 0.3s ease;

    &:hover {
      color: $green-100;
    }
  }
}
</style>
