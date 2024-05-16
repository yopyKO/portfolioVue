<template>
  <div class="about">
    <h1>Me contacter via ce formulaire</h1>
    <form @submit.prevent="submitForm" onsubmit="reset()" class="zoneSaisie">
      <input type="text" name="name" placeholder="Votre Nom et Prénom" v-model="name"/>
      <input type="email" name="email" placeholder="Votre Email" v-model="email"/>
      <input type="text" name="object" placeholder="Votre Objet" v-model="object"/>
      <textarea name="message"  placeholder="Votre Message" v-model="message" rows="7"></textarea>
      <button type="submit">Envoyer</button>
    </form>
  </div>
  
</template>

<script>
  const WEB3FORMS_ACCESS_KEY = "814682fd-a2d9-4b58-b420-81695a2f71ae";

export default {
  data() {
    return {
      name: "",
      email: "",
      object: "",
      message: "",
    };
  },
  methods: {
    async submitForm() {
      const response = await fetch("https://api.web3forms.com/submit", {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
          Accept: "application/json",
        },
        body: JSON.stringify({
          access_key: WEB3FORMS_ACCESS_KEY,
          name: this.name,
          email: this.email,
          object: this.object,
          message: this.message,
        }),
      });
      const result = await response.json();
      if (result.success) {
        console.log(result);
        alert("Message Envoyé");
      }
    },
  },
};
</script>

<style>

    .about {
      padding-bottom: 56px;
      padding-top: 220px;
      display: flex;
      flex-direction: column;
      align-content: center;
      justify-content: center;
    }

  h1{
    width: fit-content;
    padding-bottom: 3em;

  }
  .zoneSaisie{
    display: flex;
    flex-direction: column;
    gap:5px;
  }
</style>
