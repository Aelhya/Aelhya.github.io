<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from "vue";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";

interface Experience {
  id: number;
  entreprise: string;
  lieu: string;
  poste: string;
  periode: string;
  description?: string;
}

const experiences = ref<Experience[]>([
  {
    id: 0,
    entreprise: "Entreprise Individuelle",
    lieu: "Mont-de-Marsan (40)",
    poste: "Intervenante pédagogique",
    periode: "Septembre 2024 - En cours",
    description:
      "Interventions à l'École Supérieure du Numérique pour réaliser à des BAC+1 des cours d'algorithmie, de tests applications, dévelopement et maintenance web.",
  },
  {
    id: 1,
    entreprise: "Wedge Digital",
    lieu: "Bordeaux (33)",
    poste: "Product Owner / Cheffe de projet  - Alternante",
    periode: "Septembre 2022 - Septembre 2024",
    description:
      "Analyse des besoins et transformation en User Stories, gestion du backlog et priorisation des tâches. Création de devis. Planification en Gantt. Conception d’interfaces web et mobiles. Coordination entre clients et équipes projets, et gestion des retours utilisateurs. Mise en place de campagnes de test : rédaction et exécution de scénarios. Écriture de documentation.Suivi des performances via des outils de data (Google Analytics, Firebase).",
  },
  {
    id: 2,
    entreprise: "Wedge Digital",
    lieu: "Bordeaux (33)",
    poste: "Développeuse Full Stack - Alternante",
    periode: "Septembre 2021 - Septembre 2022",
    description:
      "Intégration de nouvelles fonctionnalités pour un site de formation en Django et Vue.JS et utilisation du TDD. Configuration de l'ERP ODOO pour une PME : ajout de modules personnalisés en Python et adaptation aux besoins spécifiques de gestion interne.\n" +
      "Création des interfaces, découpage du besoin et collaboration en équipe de 3 personnes.",
  },
  {
    id: 3,
    entreprise: "Wedge Digital",
    lieu: "Bordeaux (33)",
    poste: "Développeuse Full Stack - Stagiaire",
    periode: "Avril 2021 - Juin 2021",
    description:
      "Amélioration d’un site de formation en Django et Vue.JS : optimisation du SEO et amélioration de la visibilité. Réalisation de scraping en Python et utilisation de GPT-3 pour générer du contenu.",
  },
]);
const itemsToShow = ref<number>(2); // Valeur par défaut pour desktop

const updateItemsToShow = () => {
  if (window.innerWidth < 768) {
    itemsToShow.value = 1; // Mobile
  } else {
    itemsToShow.value = 2; // Desktop
  }
};

onMounted(() => {
  updateItemsToShow();
  window.addEventListener("resize", updateItemsToShow);
});

onBeforeUnmount(() => {
  window.removeEventListener("resize", updateItemsToShow);
});
</script>

<template>
  <section id="experiences">
    <div class="section-content">
      <h2>Expériences</h2>
      <Carousel :items-to-show="itemsToShow" :wrap-around="false">
        <Slide
          v-for="experience in experiences"
          :key="experience.id"
          class="timeline-item"
        >
          <div class="timeline-content">
            <h3>{{ experience.poste }}</h3>
            <p class="experience-info">
              {{ experience.entreprise }} | {{ experience.lieu }}
            </p>
            <p class="experience-info">{{ experience.periode }}</p>
            <p class="experience-description">{{ experience.description }}</p>
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
.timeline {
  &-item {
    padding: 2rem;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    background-color: #fff;
    margin-right: 2rem;
  }

  &-content {
    text-align: left;
    margin-left: 1rem;

    .experience-info,
    .experience-description {
      font-size: 1rem;
      color: #555;
      margin-bottom: 0.5rem;
    }
  }
}

h3 {
  font-size: 1.5rem;
  color: $green-700;
  margin-bottom: 0.5rem;
}

@media screen and (max-width: 768px) {
  #experiences {
    display: none;
  }
}
</style>
