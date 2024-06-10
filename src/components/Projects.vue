<script setup>
  import { ref } from "vue";
  import Modal from "./Modal.vue";
  import imageCV from "@/assets/img/CV.png";
  import specifications from "@/assets/img/CDC.png";
  import comments from "@/assets/img/EC.png";

  const isModalOpened = ref(false);

  const selectedProject = ref(null);

  const openModal = (project) => {
    isModalOpened.value = true;
    selectedProject.value=project;
  };

  const closeModal = () => {
    isModalOpened.value = false;
  };

  const projects = [
    {
      title: "Curriculum Vitae",
      date: "29 Février 2024",
      picture: imageCV,
      pictureDescription: "image d'un curriculum vitae",
      //link: "../../../CV/index.html",
      gitHubRepository: "https://github.com/juliengeoffroy/CV-JULIEN-GEOFFROY.git",
      technologies: "Html5 et Css3",

    },
    {
      title: "Cahier des charges",
      date: "25 Mai 2024",
      picture: specifications,
      pictureDescription:
        "page de garde d'un cahier des charges avec un dessin de chaussettes",
      //link: "../../../RedigerUnCahierDesCharges/cahierdescharges.pdf",
      gitHubRepository: "Non déposé sur GitHub",
      technologies: "Word",
    },
    {
      title: "Dynamiser un espace commentaires",
      date: "27 Mars 2024",
      picture: comments,
      pictureDescription: "Formulaire pour commentaires",
      //  link: "../../../DynamiserUnEspaceDeCommentaires_DocumentsDevoir/index.html",   
      gitHubRepository:"https://github.com/juliengeoffroy/espace-commentaire.git",
      technologies: "Html5, Css3 et JavaScript",
    },
  ];
</script>

<template>
  <section id="projects">
    <h1 class="title"> Mes projets </h1>
    <div class="project-container">
      <div class="project-content" v-for="(project, index) in projects" :key="index"  >
        <div @click="openModal(project)" class="project btn">
          <h2>{{ project.title }}</h2>
          <img
            :src="project.picture"
            alt="{{ project.pictureDescription }}"
          />
        </div>
      </div>
    </div>
    <Modal
      :isOpen="isModalOpened"
      @modal-close="closeModal"
      :project="selectedProject"
    >
    </Modal>
  </section>
</template>

<style scoped>

section {
  display:flex;
  justify-content: start;
  flex-direction: column;
}

section:hover > h1 {
  text-decoration: underline solid;
}

.project-container {
  display: flex;
  flex-direction:row;
  justify-content: space-around;
  height: 400px;
  }

  button {
    font-family: inherit;
    font-size: 1.2em;
    background-color: transparent;
    border-style: none;
  }

  img {
    min-width: 200px;
    height: 250px;
  }

  img:hover {
    box-shadow: 14px 12px 9px 4px rgba(97, 93, 93, 0.75);
    -webkit-box-shadow: 14px 12px 9px 4px rgba(97, 93, 93, 0.75);
    -moz-box-shadow: 14px 12px 9px 4px rgba(97, 93, 93, 0.75);
  }
</style>