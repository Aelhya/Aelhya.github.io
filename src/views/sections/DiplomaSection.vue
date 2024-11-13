<script setup lang="ts">
import { ref } from "vue";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";

interface Formation {
  id: number;
  ecole: string;
  lieu: string;
  diplome: string;
  periode: string;
  autre?: string;
  type?: string;
  description?: string;
}

const formations = ref<Formation[]>([
  {
    id: 1,
    ecole: "Ecole Supérieure Numérique des Landes (ESNL)",
    lieu: "Mont-de-Marsan (40)",
    diplome: "Mastère Manager de Solutions Digitales et Data",
    periode: "2022 - 2024",
    autre: "Diplôme délivré par l'école 3iL ingénieurs",
    type: "Formation en alternance",
    description:
      "Gestion de projet (Méthodes agiles, Méthodes prédictives), Management des SI, Big Data (Power BI), Relation client, Management des hommes, Réalité Augmentée / Réalité virtuelle.",
  },
  {
    id: 2,
    ecole: "IUT de Bordeaux",
    lieu: "Gradignan (33)",
    diplome: "Licence professionnelle DAWIN",
    periode: "2021 - 2022",
    type: "Formation en alternance",
    description:
      "Programmation web et mobile, DevOps, JEE, Méthodes agiles, Ergonomie. \nMention Très Bien.",
  },
  {
    id: 3,
    ecole: "IUT de Bordeaux",
    lieu: "Gradignan (33)",
    diplome: "DUT Informatique",
    periode: "2019 - 2021",
    description:
      "Programmation web, Conception / Programmation objet, Programmation bas niveau, Base de données, Interface Homme / Machine, Méthodes Agiles...",
  },
  {
    id: 4,
    ecole: "Lycée Victor Duruy",
    lieu: "Mont-de-Marsan (40)",
    diplome: "Baccalauréat S SI",
    periode: "2016 - 2019",
    description:
      "Sciences de l’ingénieur, spécialité Informatique et Sciences du numérique (ISN). Mention Bien",
  },
]);
</script>

<template>
  <section id="formations">
    <div class="section-content">
      <h2>Formations</h2>
      <Carousel :items-to-show="1" :wrap-around="true">
        <Slide v-for="formation in formations" :key="formation.id">
          <div class="formation-item">
            <h3>{{ formation.diplome }}</h3>
            <h4>{{ formation.ecole }} — {{ formation.lieu }}</h4>
            <p class="formation-info">
              <span>{{ formation.periode }}</span>
              -
              <span v-if="formation.type">{{ formation.type }}</span>
            </p>
            <p v-if="formation.autre">{{ formation.autre }}</p>
            <p v-if="formation.description">
              {{ formation.description }}
            </p>
          </div>
        </Slide>

        <template #addons>
          <Navigation />
          <Pagination />
        </template>
      </Carousel>
    </div>
  </section>
</template>

<style scoped lang="scss">
h2 {
  font-size: 2rem;
  color: $green-700;
  margin-bottom: 2rem;
}

h3 {
  font-size: 1.5rem;
  color: $orange-700;
  margin-bottom: 0.5rem;
}

h4 {
  color: $black;
}

.timeline-content {
  flex: 1;
  text-align: left;
  padding-left: 2rem;
}

.formation-info {
  font-size: 1rem;
  color: $black;
  font-style: italic;
  margin-bottom: 0.5rem;
}

@media screen and (max-width: 768px) {
  #formations {
    display: none;
  }
}
</style>
