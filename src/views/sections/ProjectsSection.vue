<script setup lang="ts">
import CardComponent from "../../components/CardComponent.vue";
import { ref } from "vue";

interface Projet {
  title: string;
  description: string;
  image: string;
  lien?: string;
}

const projets = ref<Projet[]>([
  {
    title: "Réalisation de portfolio",
    description:
      "Implémentation d'un portfolio pour une connaissance avec un theme en HuGo.",
    image: "https://github.com/Aelhya/Aelhya.github.io/blob/master/src/assets/img/projects_img/porfolio_lea.png?raw=true",
    lien: "https://sakki3.github.io/Portfolio/",
  },
  {
    title: "Espace client Open Source",
    description:
      "Création d’un espace client sécurisé pour la gestion de clients et le partage de documents (devis, factures).\n" +
      "L'entreprise TEMMA est notre premier Bêta-Testeur.\n" +
      "Mon rôle a été de faire la partie Gestion de projet et une partie du développement.\n" +
      "Projet collaboratif réalisé en 2022 avec PHP, Symfony et MySQL.",
    image: "https://github.com/Aelhya/Aelhya.github.io/blob/master/src/assets/img/projects_img/temma.png?raw=true",
    lien: "https://github.com/Aelhya/espace_client_temma",
  },
  {
    title: "Site de présentation de l'espace client",
    description:
      "Création d'un site pour présenter notre réflexion et notre démarche pour la conception de l'espace client Open Source.",
    image: "https://github.com/Aelhya/Aelhya.github.io/blob/master/src/assets/img/projects_img/site_presentation_espace_client_OS.png?raw=true",
    lien: "https://github.com/Aelhya/presentation_projet_innovation_numerique_2022",
  },
  {
    title: "Sokoban",
    description:
      "Projet réalisé à 3. Réalisation du jeu Sokoban sur mobile en JAVA. Il y a 3 niveaux : le premier est un plateau fait à la main, le second est un plateau importé avec un fichier texte et le dernier est un plateau stocké avec une base de données. De plus, il y a un mode administrateur permettant de gérer le niveau.",
    image: "https://github.com/Aelhya/Aelhya.github.io/blob/master/src/assets/img/projects_img/sokoban.png?raw=true",
    lien: "https://github.com/Aelhya/sokoban_dawin_a_2022",
  },
  {
    title: "Site XP Campus",
    description:
      "Participation à un projet de groupe « le Campus de nos rêves ». Dans ce projet, j'ai été graphiste et Product Owner.",
    image: "https://github.com/Aelhya/Aelhya.github.io/blob/master/src/assets/img/projects_img/xpCampus.png?raw=true",
    lien: "",
  },
  {
    title: "Site Web Component",
    description:
      "Réalisation d'un site internet pour présenter l'utilisation des Web Components",
    image: "https://github.com/Aelhya/Aelhya.github.io/blob/master/src/assets/img/projects_img/webCompo.png?raw=true",
    lien: "https://aelhya.github.io/web_components/",
  },
  {
    title: "Nuit de l'info 2020",
    description:
      "Participation à cette compétition informatique où il faut répondre à des défis dans un temps limité. Equipe : BA$HROOM." +
      "Nous sommes arrivés 2ème de France au défi « Neurchi Illuminati ».",
    image: "https://github.com/Aelhya/Aelhya.github.io/blob/master/src/assets/img/projects_img/Logo_defi.png?raw=true",
    lien: "https://aelhya.github.io/web_components/",
  },
  {
    title: "Sunny",
    description:
      "Site réalisé au lycée comme projet final pour la spécialité Informatique et Sciences du Numériques en Terminale. Projet fait en groupe. Langages : HTML, CSS, JS, Python, Arduino.",
    image: "https://github.com/Aelhya/Aelhya.github.io/blob/master/src/assets/img/projects_img/sunny.png?raw=true",
    lien: "https://www.youtube.com/watch?v=ciSc-jTICgs",
  },
  {
    title: "Self-e",
    description:
      "Projet réalisé au lycée dans le cadre des Travaux Pratiques Encadrés (TPE) et  présenté aux Olympiades de Sciences de l'Ingénieur en 2018. Projet fait en groupe. " +
      "Langages : HTML, CSS, JS, PhP, Android.",
    image: "https://github.com/Aelhya/Aelhya.github.io/blob/master/src/assets/img/projects_img/selfe.JPG?raw=true",
    lien: "https://www.youtube.com/watch?v=ciSc-jTICgs",
  },
]);
</script>

<template>
  <section id="projects">
    <div class="section-content">
      <h2>Projets</h2>
      <div class="projets-grid">
        <div v-for="projet in projets" :key="projet.title" class="projet-card">
          <CardComponent
            class="projetCard"
            :image="projet.image"
            :title="projet.title"
            :description="projet.description"
            :lien="projet.lien"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.projets-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;
}

.projet-card {
  &:hover {
    transform: translateY(-10px);
  }
}

@media screen and (max-width: 768px) {
  .projet-card {
    width: 100%;
  }
}
</style>
