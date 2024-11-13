<script setup lang="ts"></script>

<template>
  <a
    href="../assets/doc/CV_LOUIS_Adelaide.pdf"
    download
    class="download-button"
  >
    <span class="download-text">Télécharger mon CV</span>
    <span class="download-icon">&#8681;</span>
  </a>
</template>

<style scoped lang="scss">
.download {
  &-button {
    display: inline-block;
    padding: 10px 20px;
    background-color: $green-700;
    color: white;
    text-decoration: none;
    border-radius: 5px;
    transition:
      background-color 0.3s ease,
      transform 0.3s ease;

    &:hover {
      background-color: $green-500;
      transform: translateY(-5px);
    }

    &:active {
      background-color: $green-300;
      transform: translateY(0) scale(0.95);
    }
  }

  &-text {
    margin-right: 10px;
  }

  &-icon {
    font-size: 18px;
    vertical-align: middle;
  }
}
</style>
