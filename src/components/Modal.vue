<script setup>
  import { defineProps, defineEmits } from "vue";

  const props = defineProps({
    isOpen: Boolean,
    openModal: Function,
    project: Object,
  });

  const emit = defineEmits(["modal-close"]);
</script>

<template>
  <div class="bloc-modale" v-if="isOpen">
    <div @click.stop="emit('modal-close')" class="overlay"></div>
  
    <div class="modale">
      <button
        @click.stop="emit('modal-close')"
        @click="openModal(project)"
        class="btn-modale">
        <img
          src="../assets/img/bouton-fermer.png"
          alt="bouton de fermeture"
        />
      </button>
      <div class="content-modale">
        <h2>{{ props.project.title }}</h2>
  
        <p>Date de création : {{ props.project.date }},</p>
        <p></p>
        <p>Technologies utilisées: {{ props.project.technologies }}</p>
        <p>
          <a href="/page404" target="_blank">
            Lien vers la création
          </a>
        </p>
        <p>
          <a href="https://github.com/juliengeoffroy" target="_blank">
            Lien du Repository
          </a>
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .bloc-modale {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-size: 1.5em;
  }

  .overlay {
    background-color: rgba(0, 0, 0, 0.188);
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
  }

  .modale {
    background: rgba(250, 249, 249, 0.866);
    color: #333;
    padding: 50px;
    position: fixed;
    top: 30%;
    border-radius: 15%;
    border-style: double;
    border-width: 10px;
    border-color: rgb(40, 150, 131);
  }

  button {
    position: absolute;
    top: 10px;
    right: 10px;
    border-style: none;
    background-color: transparent;
  }

  h2 {
    padding-bottom: 20px;
  }

</style>