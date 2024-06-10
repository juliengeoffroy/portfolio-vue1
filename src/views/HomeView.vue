<script setup>
import Entete from "@/components/Header.vue";
import Projects from "@/components/Projects.vue";
import Contact from "@/components/Contact.vue";
import Pieddepage from "@/components/Footer.vue";
import Apropos from "@/components/Apropos.vue";
</script>

<template>
  <div class="homeView" id="homeView">
    <header>
      <div>
        <Entete />
      </div>
    </header>
    <main>
      <div class="home-main-content">
        <div>
          <Apropos />
        </div>
        <div>
          <Projects />
        </div>
        <div>
          <Contact/>
        </div>
      </div>
      <aside>
        <button>
          <a href="#homeView" id="up-button">
            <img
              src="../assets/img/fleche_haut.png"
              alt="flêche pointant vers le haut"
            />
          </a>
        </button>
      </aside>
    </main>
    <footer>
      <Pieddepage />
    </footer>
  </div>
</template>

<style scoped>
  main{
    display: flex;
    flex-direction: row;
    padding: 10px;
  }

  aside{
    display: flex;
  }

  button {
    background: transparent;
    border-style: none;
    position: fixed;
    bottom: 50px;
    right :50px;
  }

</style>