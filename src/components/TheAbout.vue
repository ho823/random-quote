<template>
  <div id="content-about">
    <img id="img-team" src="@/assets/business-team.jpg" />
    <div id="elm-decoration"></div>
    <p id="text-about">Unde Rufinus ea tempestate praefectus praetorio ad discrimen trusus est ultimum. ire enim ipse compellebatur ad militem, 
      quem exagitabat inopia simul et feritas, et alioqui coalito more.</p>
  </div>
  </template>
  
  <script setup lang="ts"> 
  </script>
  
  <style>

  #content-about {
    height: 100vh;
    width: 50rem;
    padding: 5rem;
    position: relative;
  }

  #elm-decoration {
    width: 10rem;
    height: 10rem;
    background-color: aqua;
    position: absolute;
    top: 40rem;
    right: 6rem;
  }

  #img-team {
    height: 70vh;
    width: 35rem;
    object-fit: cover;
  }

  #text-about {
    color: #FFFF;
    background-color: rgba(23, 23, 23, 0.498);
    padding: 1rem;
    position: absolute;
    z-index: 1000;
    top: 20rem;
    left: 11rem;
    width: 45%;
  }

  </style>
  
  