<script setup lang="ts">
const props = defineProps({
  image: String,
  title: String,
  description: String,
  lien: String,
});
</script>

<template>
  <div class="card">
    <img v-if="props.lien != ''" :src="props.image" :alt="props.title" class="card-image" />
    <div class="card-content">
      <h3 class="card-title">{{ props.title }}</h3>
      <p class="card-description">{{ props.description }}</p>
      <div v-if="props.lien != ''">
        <a :href="props.lien" class="card-button" target="_blank"
          >En savoir plus</a
        >
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 300px;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  background-color: white;
  overflow: hidden;
  cursor: pointer;
  transition: transform 0.3s ease;

  &:hover {
    transform: translateY(-10px);
  }
}

.card-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.card-content {
  padding: 20px;
  text-align: center;
}

.card-title {
  font-size: 1.5rem;
  color: $green-700;
  margin-bottom: 0.5rem;
}

.card-description {
  font-size: 1rem;
  color: $black;
  margin-bottom: 1rem;
}

.card-button {
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  background-color: $green-700;
  color: white;
  cursor: pointer;
  transition: background-color 0.3s ease;

  &:hover {
    background-color: $green-300;
  }
}
</style>
