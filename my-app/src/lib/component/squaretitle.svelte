
<div class="squaretitle"></div>

<style>
.squaretitle {
  position: absolute;
  width: 200px;
  height: 800px;
  left: 50%;
  top: 50%;
  background: linear-gradient(180deg, #131939 0%, #1A2246 50%, #303D6E 100%);
  border-radius: 30px;
  transform: translate(-50%, -50%) rotate(-90deg);
  display: flex;
  flex-direction: column-reverse;
  justify-content: flex-start;
  
  /* Ajout des règles CSS pour rendre le bloc squaretitle responsive */
  max-width: 100%; /* Le bloc squaretitle occupe 100% de la largeur de l'écran */
  max-height: 100%; /* Le bloc squaretitle occupe 100% de la hauteur de l'écran */
  height: auto; /* La hauteur du bloc squaretitle s'adapte au contenu */
  top: 10%; /* Décalage vers le haut */
  left: 0; /* Alignement à gauche */
  transform: none; /* Suppression de la rotation */
}

/* Règle CSS pour les écrans de taille inférieure à 768px */
@media screen and (max-width: 767px) {
  .squaretitle {
    width: 150px; /* Réduction de la largeur */
    height: auto; /* La hauteur du bloc squaretitle s'adapte au contenu */
    top: 0; /* Alignement en haut */
    left: 50%; /* Centrage horizontal */
    transform: translate(-50%, 0) rotate(0); /* Annulation de la rotation */
    border-radius: 15px; /* Réduction du rayon de bordure */
  }
}


</style>    