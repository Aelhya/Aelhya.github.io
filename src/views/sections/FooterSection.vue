<script setup lang="ts">

import SocialNetworkComponent from "../../components/SocialNetworkComponent.vue";

let currentYear: number = new Date().getFullYear();
</script>

<template>
  <footer id="contact">
    <div class="contact-content">
      <div class="contact-info">
        <h2>Contact</h2>
        <p>
          Email :
          <a href="mailto:adelaide.louis@gmail.com">adelaide.louis@gmail.com</a>
        </p>
        <p>Portable : 07 . 86 . 41 . 15 . 32</p>

        <SocialNetworkComponent />
      </div>
      <div class="copyright">
        <p>
          Copyright © Adélaïde LOUIS {{ currentYear }}. Tous droits réservés.
        </p>
      </div>
    </div>
  </footer>
</template>

<style scoped lang="scss">
#contact {
  background-color: $green-700;
  color: $white;
  padding: 2rem;
  text-align: center;
}

h2 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

p {
  font-size: 1rem;
  margin-bottom: 0.5rem;
}
a {
  color: $white;

  &:hover {
    color: $yellow-050;
  }
}

.social-media {
  margin-top: 1rem;
}

.social-media-link {
  color: $white;
  font-size: 1.5rem;
  transition: color 0.2s;

  &:hover {
    color: $green-100;
  }
}

.copyright {
  font-size: 0.875rem;
  color: $green-100;
}
</style>
