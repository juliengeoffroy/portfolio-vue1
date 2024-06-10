
<template>
  <router-view></router-view>
</template>

<style >
@import url('https://fonts.googleapis.com/css2?family=Allura&family=Lato:ital,wght@0,400;0,700;1,400&display=swap');

@font-face {
  font-family: "Nickainley";
  src: url('../src/assets/fonts/Nickainley-Normal.ttf.woff')
}

#app{
  font-family: "Nickainley";
  font-weight: 500;
  font-size: 1rem;
  padding: 2em;
  background-image: url(../src/assets/img/OL.png);
  background-size: cover;
  min-width: 85vw;
  min-height: 90vh;

}

h1,h2 {
  font-family: "Allura", cursive;
  font-weight: 800;
 }

h1 {
  font-size: 3.5rem;
}

h2 {
  font-size: 2.5rem;
}

</style>