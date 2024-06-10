<script setup>
   import { Menu, MenuButton, MenuItems, MenuItem } from "@headlessui/vue";
</script>

<template>
  <div class="header">
    <div class="img">
      <figure>
        <a ref="/page404" target="_blank">
          <img src="../assets/img/logo.png" alt="image logo">
        </a>
      </figure>
    </div>
    <Menu as="div" class="menu">
      <div>
        <MenuButton class="menu-label">
          <img
            src="../assets/img/barre-menu.png"
            alt="Barre de menu"
          >
          Accueil
          <img 
            src="../assets/img/chevron-bas.png" 
            alt="chevron descendant"
            class="chevron"
          >
        </MenuButton>
      </div>
      <transition
        enter-active-class="transition duration-100 ease-out"
        enter-from-class="transform scale-95 opacity-0"
        enter-to-class="transform scale-100 opacity-100"
        leave-active-class="transition duration-75 ease-in"
        leave-from-class="transform scale-100 opacity-100"
        leave-to-class="transform scale-95 opacity-0"
      >
        <MenuItems>
          <div class="menu-items">
            <MenuItem v-slot="{ active }">
              <button class="menu-list">
                <a href="#about">Qui suis-je ?</a>
              </button>
            </MenuItem>
            <MenuItem v-slot="{ active }">
              <button class="menu-list">
                <a href="#projects">Mes projets</a>
            </button>
            </MenuItem>
            <MenuItem v-slot="{ active }">
              <button class="menu-list">
                <a href="#contact">Contact</a>
              </button>
            </MenuItem>
          </div>
        </MenuItems>
      </transition>
    </Menu>
    <Menu as="div" class="menu">
      <div>
        <MenuButton class="menu-label">
          Projets à Télécharger
          <img 
            src="../assets/img/chevron-bas.png" 
            alt="chevron descendant"
            class="chevron"
          >
        </MenuButton>
      </div>
      <transition
        enter-active-class="transition duration-100 ease-out"
        enter-from-class="transform scale-95 opacity-0"
        enter-to-class="transform scale-100 opacity-100"
        leave-active-class="transition duration-75 ease-in"
        leave-from-class="transform scale-100 opacity-100"
        leave-to-class="transform scale-95 opacity-0"
      >
        <MenuItems>
          <div class="menu-items">
            <MenuItem v-slot="{ active }">
              <button class="menu-list">
                <a href="./CV.pdf" download="Curriculum Vitae !">
                  <button>Télécharger Curriculum Vitae !</button>
                </a>
              </button>
            </MenuItem>
            <MenuItem v-slot="{ active }">
              <button class="menu-list">
                <a href="./cahier-des-charges.pdf" download="Cahier des Charges !">
                  <button>Télécharger Cahier des charges !</button>
                </a>
              </button>
            </MenuItem>
          </div>
        </MenuItems>
      </transition>
    </Menu>
  </div>
</template>
  
<style scoped>
  .header {
    display: flex;
    align-items: center;
    justify-content: end;
    height: 150px;
    margin-right: 10px;
    column-gap: 50px;
  }
  
  .menu-label{
    display: flex;
    width: 100%;
    align-items: center;
    border-style:none ;
    background-color:transparent;
    font-family: inherit;
    font-size: 2em;
    font-weight: 500;  
  }
  
  .menu-label:hover {
    text-decoration: underline solid;
  }
  
  .menu-items{
    position: fixed;
  }
  
  .chevron{
    width:15px;
    padding-top: 25px;
  }
  
  .menu-list {
    display: flex;
    flex-direction: column;
    border-style: none;
    margin-left: 20px;
    background-color: transparent;
    font-family: inherit;
    font-size: 1.5em;
  }
  
  .menu-list:hover {
    text-decoration: underline solid;
  }
  
  a{
    text-decoration: none;
    color: black;
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

</style>
  