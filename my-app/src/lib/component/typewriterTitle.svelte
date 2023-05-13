<script lang="ts">
  import { onMount } from 'svelte';
  
  const sentences = ["Build the best Discord servers", "Build the best Discord servers", "Build the best Discord servers"];
  let currentSentence = "";
  let currentIndex = 0;

  function typeNext() {
    if (currentIndex >= sentences.length) {
      currentIndex = 0;
    }
    
    const sentence = sentences[currentIndex];
    const remainingChars = sentence.slice(currentSentence.length);
    
    if (remainingChars.length > 0) {
      currentSentence += remainingChars.charAt(0);
      setTimeout(typeNext, 100);
    } else {
      setTimeout(deleteCurrent, 1000);
    }
  }
  
  function deleteCurrent() {
    const remainingChars = currentSentence.slice(0, -1);
    currentSentence = remainingChars;
    
    if (remainingChars.length > 0) {
      setTimeout(deleteCurrent, 100);
    } else {
      currentIndex++;
      typeNext();
    }
  }

  onMount(() => {
    typeNext();
  });
</script>

<div class=title><strong>{currentSentence}</strong></div>


<style>
.title {
  font-family: "Uni Sans Demo", sans-serif;
  color: white;
  position: absolute;
  top: 20%;
  left: 10%;
  font-size: 41px;
  display: flex;
  flex-direction: column-reverse;
  justify-content: flex-start;
  
  /* Ajout des règles CSS pour rendre le titre responsive */
  width: 80%; /* Le titre occupe 80% de la largeur de l'écran */
  max-width: 800px; /* La largeur maximale du titre est de 800px */
  margin: 0 auto; /* Centrage horizontal du titre */
  text-align: center; /* Centrage vertical du texte */
}

/* Règle CSS pour les écrans de taille inférieure à 768px */
@media screen and (max-width: 767px) {
  .title {
    font-size: 28px; /* Réduction de la taille de la police */
    top: 10%; /* Décalage vers le haut */
    left: 0; /* Alignement à gauche */
    width: 100%; /* Le titre occupe toute la largeur de l'écran */
    max-width: none; /* Pas de limite de largeur maximale */
    justify-content: center; /* Centrage vertical du texte */
  }
}


</style>
