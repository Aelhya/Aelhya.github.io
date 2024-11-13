<script setup lang="ts">
import { ref } from "vue";
import { Icon } from "@iconify/vue";

interface SkillSet {
  title: string;
  icon: string;
  skills: string[];
}

const skillSets = ref<SkillSet[]>([
  {
    title: "Gestion de projet",
    icon: "eos-icons:project-outlined",
    skills: [
      "Méthodes Agiles (Scrum, Kanban)",
      "Méthodes Traditionnelles (Waterfall, Cycle en V)",
      "Suivi de l avancement du projet",
      "Rédaction de Cahier des Charges",
      "Rédaction de documentation",
    ],
  },
  {
    title: "Gestion du produit",
    icon: "ix:product",
    skills: [
      "Analyse du besoin",
      "Rédaction de User Stories",
      "Gestion du Backlog",
    ],
  },
  {
    title: "Programmation Web",
    icon: "hugeicons:web-design-02",
    skills: [
      "HTML",
      "CSS",
      "JavaScript",
      "Django",
      "VueJS",
      "Symfony",
      "Bootstrap",
    ],
  },
  {
    title: "Programmation Objet",
    icon: "arcticons:uml-class-editor",
    skills: ["Python", "Java", "C#"],
  },
  {
    title: "Base de données",
    icon: "material-symbols-light:database",
    skills: ["SQL - SSMS, Oracle SQL Developer", "PostgreSQL"],
  },
  {
    title: "Outils de collaboration",
    icon: "streamline:collaborations-idea",
    skills: [
      "GitHub / GitLab",
      "Zenhub / Trello",
      "Figma / Miro",
      "Confluence",
    ],
  },
  {
    title: "Autres",
    icon: "icons8:plus",
    skills: [
      "Docker",
      "TDD (Test Driven Development)",
      "Logiciels de PAO (Krita)",
    ],
  },
]);
</script>

<template>
  <section id="skills">
    <div class="section-content">
      <h2>Compétences</h2>
      <div class="skills-list">
        <div
          v-for="skillSet in skillSets"
          :key="skillSet.title"
          class="skill-card"
        >
          <div class="skill-card__header">
            <h2 class="skill-card__title">
              <span><Icon :icon="skillSet.icon" class="icon" /></span>
              <span>{{ skillSet.title }}</span>
            </h2>
          </div>
          <ul class="skill-card__list">
            <li
              v-for="skill in skillSet.skills"
              :key="skill"
              class="skill-set__item"
            >
              {{ skill }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
#skills {
  .section-content {
    max-width: 1200px;
    margin: 0 auto;

    h2 {
      font-size: 2.5rem;
      margin-bottom: 20px;
      color: $black;
    }

    .skills-list {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;

      .skill-card {
        background-color: #fff;
        border: 1px solid $gray-050;
        border-radius: 8px;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        margin: 10px;
        padding: 20px;
        text-align: left;
        width: calc(33.333% - 20px);
        transition: transform 0.3s ease;

        &:hover {
          transform: translateY(-10px);
        }

        @media (max-width: 768px) {
          width: calc(50% - 20px);
        }

        @media (max-width: 480px) {
          width: 100%;
        }

        .skill-card__header {
          .skill-card__title {
            font-size: 1.5rem;
            margin: 0;
            color: #333;
            display: flex;
            align-items: center;

            .icon {
              margin-right: 10px;
              font-size: 1.5rem;
              color: $orange-300;
            }
          }
        }

        .skill-card__list {
          list-style: none;
          padding: 0;
          margin: 0;

          .skill-set__item {
            font-size: 1rem;
            color: $green-700;

            &:last-child {
              margin-bottom: 0;
            }
          }
        }
      }
    }
  }
}
</style>
