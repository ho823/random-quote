<template>
  <div class="bg-quotes">
    <p id="title">Random quote</p>
    <button @click="randomQuote">Click to change quote</button>
    <div v-if="quote">
      <div id="content-quote" v-for="{content, author} in quote">
      <q>{{ content }}</q>
      <p id="author">{{ author }}</p>
    </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

interface Quote {
  content: string;
  author: string;
}

const quote = ref<Quote | null>(null);

const randomQuote = () => {
  fetch('https://api.quotable.io/quotes/random')
    .then(response => response.json())
    .then(data => {
      quote.value = data;
    })
    .catch(error => {
      console.error('Une erreur s\'est produite lors de la récupération de la citation :', error);
    });
};
</script>

<style>
.bg-quotes {
  background-image: url("@/assets/sea.jpg");
  height: 50rem;
  height: 100vh;
  background-size: cover;
  width: 50rem;
  padding: 5rem;
}

#title {
  font-weight: bold;
  font-size: 2rem;
  letter-spacing: .58ch;
}

button {
  background-color: #FFFF;
  color: #43141a ;
  border: none;
  border-radius: 2rem;
  padding: 0.75rem 1rem;
  cursor: pointer;
  margin-top: 3rem;
  text-transform: uppercase;
  box-shadow: 3px -2px 20px -10px rgba(0,0,0,0.28);
}

button:hover {
  background-color: rgba(22, 22, 22, 0.578);
  color: #FFFFFF;
}

#content-quote {
  margin-top: 5rem;
  font-weight: bold;
  position: relative;
}

#author {
  margin-top: 1rem;
  font-size: 0.75rem;
  text-align: right;
  font-style: italic;
}

q::before {
  font-size: 5rem;
  color: cyan;
  font-family: 'Catamaran', sans-serif;
}

q::before {
  position: absolute;
  top: -3.5rem;
  left: -1rem;
}

q::after {
  display: none;
}

</style>

