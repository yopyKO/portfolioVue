<script setup>
  import WelcomeItem from './WelcomeItem.vue'
  import DocumentationIcon from './icons/IconDocumentation.vue'
  import ToolingIcon from './icons/IconTooling.vue'
  import EcosystemIcon from './icons/IconEcosystem.vue'
  import CommunityIcon from './icons/IconCommunity.vue'
  import SupportIcon from './icons/IconSupport.vue'
  import Contenu from './contenu.vue'
  import Contenu1 from './contenu1.vue'
  import Contenu2 from './contenu2.vue'
  import Contenu3 from './contenu3.vue'
</script>

<template>
<div class="welcomeVue">
  <WelcomeItem>
    <template #icon>
      <DocumentationIcon />
    </template>
    <template #heading>CV en Ligne</template>
    <template #image>
      <img class="imgItem" src="../assets/cv.item.png" alt="code du cv en ligne">
      <contenu></contenu>
    </template>
    <br>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <ToolingIcon />
    </template>
    <template #heading>Rédaction d'un cahier des charges pour la création dun site WEB</template>
    <template #image>
      <img class="imgItem" src="../assets/maquette.item.png" alt="image maquette">
      <contenu1></contenu1>
  </template>
   <br>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      
      <CommunityIcon />
    </template>
    <template #heading>Création d'un espace commentaires</template>
    <template #image>
      <img class="imgItem" src="../assets/com.item.png" alt="code js de l'espace com">
      <contenu2></contenu2>
  </template>
  
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <EcosystemIcon />
    </template>
    <template #heading>Portfolio</template>
    <template #image>
      <img class="imgItem" src="../assets/portfolio.item.png" alt="code du cv en ligne">
      <contenu3></contenu3>
  </template>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <SupportIcon />
    </template>
    <template #heading>Support de Cours C.E.F.</template>
    <template #image>
      <a href="https://www.centre-europeen-formation.fr/" target="_blank">Lien vers le site</a>
    </template>
  </WelcomeItem>
</div>
</template>

<style>
  .imgItem{
    width: 3em;
    height: 3em;
  }
  .welcomeVue{
    padding-top: 220px;
    margin-bottom: 20px;
  }
</style>