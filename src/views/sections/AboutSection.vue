<script setup>
import ButtonDownloadComponent from "../../components/ButtonDownloadComponent.vue";
</script>

<template>
  <!-- À propos -->
  <section id="about">
    <div class="section-content">
      <h2>À propos</h2>
      <div class="section-content__div">
        <div>
          <img
            class="hero-img"
            src="../../assets/img/avatar.jpg"
            alt="Avatar dessiné par Adélaïde LOUIS"
          />
        </div>
        <div>
          <p>
            Diplômée d'un mastère <b>Manager de Solutions Digitales et Data</b>,
            j'apprécie penser à des solutions pouvant améliorer le quotidien des
            utilisateurs.
          </p>
          <p>
            J'ai appliqué mes compétences dans des domaines qui me tiennent à
            coeur à savoir : la <b>gestion de projet</b> et le <b>web</b>.
          </p>
          <p>
            En plus de ma passion pour l'IT, je m'intéresse à l'<b
              >art digital</b
            >.
          </p>
          <p>
            Le challenge ne me fait pas peur : au contraire, j'adore relever
            toutes sortes de défis !
          </p>
          <p>
            Si vous souhaitez que nous collaborions ensemble, n'hésitez pas à
            consulter mon CV !
          </p>
          <ButtonDownloadComponent />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.section-content__div {
  display: grid;
  grid-template-columns: 1fr 4fr;
}
.hero-img {
  width: 100%;
  border-radius: 40%;
  object-fit: cover;
  border: 3px solid $green-700;
}

@media screen and (max-width: 768px) {
  .section-content__div {
    display: grid;
    grid-template-columns: 1fr;
  }
  .hero-img {
    display: none;
  }
}
</style>
