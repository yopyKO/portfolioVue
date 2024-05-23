<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <h3>
      Bonjour, je m'appelle Grosbois Charly, je suis actuellement en reconversion professionnelle et je me forme dans le but de devenir développeur full Stack et voici mon portfolio...
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (max-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
    display:none;
  }
}
</style>
