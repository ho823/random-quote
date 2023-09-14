<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">
          <div class="link_word">
            <span class="link_letter">Q</span>
            <span class="link_letter">u</span>
            <span class="link_letter">o</span>
            <span class="link_letter">t</span>
            <span class="link_letter">e</span>
          </div>
        </RouterLink>
        <RouterLink to="/about">
          <div class="link_word">
            <span class="link_letter">A</span>
            <span class="link_letter">b</span>
            <span class="link_letter">o</span>
            <span class="link_letter">u</span>
            <span class="link_letter">t</span>
          </div>
        </RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

body {
  font-family: 'Krub', sans-serif;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
}

nav a {
  display: inline-flex;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}


@keyframes move {
  from {
    transform: translateY(0) translateZ(0);
  }
  to {
    transform: translateY(1.2em) translateZ(0);
    transition: transform .4s ease, background-color;
  }
}


.link_word{
  text-shadow: 0 calc(1.2em*-1) 0 rgb(6, 138, 138);
  overflow: hidden;
  display: flex;
  transform: translateY(0) translateZ(0);
  transition: transform .4s ease;
  transition: color 2s;
}

.link_word:hover > * {
  animation: move 1s;
  animation-fill-mode: forwards;
}

.link_word:focus {
  background-color: blue;
}

.link_letter {
  backface-visibility: visible;
  display: block;
  font-style: normal;
}

.link_letter:first-child {
  transition-delay: .05s;
}

.link_letter:nth-child(2) {
  transition-delay: .1s;
}

.link_letter:nth-child(3) {
  transition-delay: .15s;
}

.link_letter:nth-child(4) {
  transition-delay: .2s;
}

.link_letter:nth-child(5) {
  transition-delay: .25s;
}


@media (min-width: 1024px) {
  header {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  nav {
    text-align: left;
    font-size: 1rem;
  }
}
</style>
