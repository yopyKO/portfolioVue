<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'

</script>

<template>
  <header>
    <RouterLink to="/"><img alt="Vue logo" class="logo" src="@/assets/yopykoLOGO.jpeg" width="125" height="125" /></RouterLink>
    
    <div class="wrapper">
      <HelloWorld msg="Portfolio YopyKO" />
      <nav>
        <RouterLink to="/">Accueil</RouterLink>
        <RouterLink to="/about">Me contacter</RouterLink>   
        <RouterLink to="/404">À propos</RouterLink>   
      </nav>
    </div>
  </header>


  <footer>
    <div class="network">
            <a href="https://www.linkedin.com/in/charly-grosbois-197294a7/"  target="_blank">
                <img class="networkPicture" src="./assets/linkedin.png" alt="logo de LinkedIn">
            </a>
            <a href="https://github.com/yopyKO/" target="_blank">
                <img class="networkPicture" src="./assets/connexion.png" alt="logo de Github">
            </a>
        </div>
        <div class="date">
            <small>Dernière mise à jour le <time datetime="2024-02-27">16 mai 2024</time></small>
        </div>
  </footer>
  <RouterView />
</template>

<style scoped>

  header {
    line-height: 1.5;
    max-height: 100vh;
    top: 0px;
    position: fixed;
    z-index: 101;
    background-color: rgb(0, 3, 2);
    width: 100%;
  }
  footer {
    display: flex;
    flex-direction: row-reverse;
    align-content: center;
    justify-content: center;
    align-items: center;
    position: fixed;
    bottom: 0PX;
    background-color: hsla(160, 100%, 37%, 1);
    width: 100% ;
    z-index: 101;
  }
  .logo {
    display: block;
    margin: 0 auto 2rem;
    border-radius: 35%;
  }

  nav {
    width: 100%;
    font-size: 12px;
    text-align: center;
    margin-top: 2rem;
  }

  nav a.router-link-exact-active {
    color: var(--color-text);
  }

  nav a.router-link-exact-active:hover {
    background-color: transparent;
  }

  nav a {
    display: inline-block;
    padding: 0 1rem;
    border-left: 1px solid var(--color-border);
  }

  nav a:first-of-type {
    border: 0;
  }

  @media (min-width: 1024px) {
    header {
      display: flex;
      place-items: center;
      padding-right: calc(var(--section-gap) / 2);
      max-width: 100%;
      position: fixed;
    }
    
    .logo {
      margin: 0 2rem 0 0;
    }

    header .wrapper {
      display: flex;
      place-items: flex-start;
      flex-wrap: wrap;
    }

    nav {
      text-align: left;
      margin-left: -1rem;
      font-size: 1rem;

      padding: 1rem 0;
      margin-top: 1rem;
    }
    
  }
  .networkPicture{
    margin: 10px 30px 10px 30px;
    height: 2em;
    width: 2em ;
  }
  @media (max-width: 400px) {
    footer {
      max-height: 80px;
      display: flex;
      flex-wrap: wrap;
      position: fixed;
      bottom: 0px;
    }}
</style>
