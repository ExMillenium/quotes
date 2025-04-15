<template>
  <div class="app">
    <h1>Citations Inspirantes</h1>
    <div class="citation">
      <img :src="currentQuote.authorImage" alt="Author's image" class="author-image" />
      <p>{{ currentQuote.text }}</p>
      <p class="author">– {{ currentQuote.author }}</p>
    </div>
    <button @click="generateQuote">Nouvelle Citation</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Liste des citations inspirantes avec des images générées dynamiquement
const quotes = [
  { 
    text: "Le succès est la somme de petits efforts répétés jour après jour.", 
    author: "Leo Robert Collier", 
    authorImage: `https://ui-avatars.com/api/?name=Leo+Robert+Collier&background=random`
  },
  { 
    text: "Croyez en vous et en tout ce que vous êtes.", 
    author: "Christian D. Larson", 
    authorImage: `https://ui-avatars.com/api/?name=Christian+D.+Larson&background=random`
  },
  { 
    text: "Faites de votre vie un rêve, et d’un rêve, une réalité.", 
    author: "Antoine de Saint-Exupéry", 
    authorImage: `https://ui-avatars.com/api/?name=Antoine+de+Saint-Exupery&background=random`
  },
  { 
    text: "La vie est ce qui se passe quand on est occupé à faire d'autres projets.", 
    author: "John Lennon", 
    authorImage: `https://ui-avatars.com/api/?name=John+Lennon&background=random`
  },
  { 
    text: "Vous ne trouvez pas le bonheur, vous le créez.", 
    author: "Camilla Eyring Kimball", 
    authorImage: `https://ui-avatars.com/api/?name=Camilla+Eyring+Kimball&background=random`
  },
];

// Référence pour la citation actuelle
const currentQuote = ref(quotes[0]);

// Fonction pour générer une nouvelle citation aléatoire
const generateQuote = () => {
  const randomIndex = Math.floor(Math.random() * quotes.length);
  currentQuote.value = quotes[randomIndex];
};
</script>

<style scoped>
.app {
  max-width: 600px;
  margin: 2rem auto;
  padding: 1rem;
  text-align: center;
  font-family: 'Arial', sans-serif;
}

.citation {
  margin-bottom: 1rem;
  font-size: 1.2rem;
  font-style: italic;
}

.author {
  margin-top: 0.5rem;
  font-weight: bold;
}

button {
  padding: 0.6rem 1.2rem;
  font-size: 1rem;
  background-color: #5c6bc0;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
}

button:hover {
  background-color: #3f51b5;
}

.author-image {
  max-width: 100px;
  border-radius: 50%;
  margin-bottom: 1rem;
}
</style>