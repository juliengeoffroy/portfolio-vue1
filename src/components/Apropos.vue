<template>
  <section class="apropos" id="apropos">
    <h1 class="title">A Propos </h1>
    <div class="flex-container">
      <div class="img">
        <figure>
          <a href="/page404" target="_blank">
            <img src="../assets/img/me.jpg" alt="Image de Profil">
          </a>
        </figure>
      </div>
      <div class="Apropos_text">
        <p>
          Je m'appelle Julien Geoffroy, j'ai 35 ans et je suis célibataire.
          Je travaille actuellement depuis 2009 dans une entreprise d'Agro-Alimentaire: Maison Monterrat ( Groupe Valentin Traiteur), qui situe dans le 01 à Feillens. 
          Toujours passionné d'informatique, c'est pour sa que j'ai décider de faire cette formation.
        </p>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>

  .flex-container{
    display: flex;
    flex-direction: row;
    align-items: center;
  }

  .apropos {
    align-items: center;
    font-size: 1.2em;
  }

  section:hover > h1 {
    text-decoration: underline solid;
  }

  figure {
    display: flex;
    align-items: center;
    width: 200px;
    height: 200px;
    padding-right :2em;
  }

  figure img {
    width: 100%;
    height: 100%;
    border-radius: 15%;
  }

  p {
    text-indent: 50px;
  }

</style>