<script setup>
    import { ref } from 'vue'
    import MyModal from '@/components/MaModale.vue'
    const works = ref([
        {
            id: 1,
            title: "CV en Ligne",
            date: "Crée le 29 février 2024",
            desc: "HTML, CSS",
            image: "achievement-1",
            link: "https://github.com/yopyKO/CV_devoir",
        },
        {
            id: 2,
            title: "Rédaction d'un Cahier des Charges",
            date: "Crée le 14 mars 2024",
            desc: "PDF",
            image: "achievement-2",
            link: "https://drive.google.com/file/d/10jBFh2dOXouCUjCzfyojNWVpUSagrHnd/view?usp=drive_link",
        },
        {
            id: 3,
            title: "Création d'un Espace Commentaires",
            date: "Crée le 12 avril 2024",
            desc: "HTML, CSS, JavaScript",
            image: "achievement-3",
            link: "https://github.com/yopyKO/DynamiserEspaceCom",
        },
        {
            id: 4,
            title: "PortFolio",
            date: "09/2023-11/2023",
            desc: "HTML, CSS, JavaScript, VUE.JS",
            image: "achievement-4",
            link: "/",
        }
    ])
    const selectedProject = ref({});
    const isModalOpened = ref(false);
    
    const openModal = (work) => {
        selectedProject.value = work;
        isModalOpened.value = true;
    };
    const closeModal = () => {
        isModalOpened.value = false;
    };
</script>
<template>
    <div id="my_achivements">
        <h2>Mes réalisations</h2>
        <section v-for="work  in works" :key="work.id">
            <h3>{{ work.title }}</h3>
            <button @click="openModal(work)">
                <img :src="`/src/assets/${work.image}.png`" :alt="`${work.image}`">
            </button>
            <MyModal :currentProject="selectedProject" :isOpen="isModalOpened" @modal-close="closeModal" name="first-modal">
                <template #title>
                </template>
                <template #content>
                </template>
                <template #footer>
                </template>
            </MyModal>
        </section>
    </div>
</template>
<style scoped>

div {
    margin-bottom: 2rem;
}

h3:first-of-type {
    margin-top: 1rem;
}

h3 {
    width: fit-content;
    margin: auto;
    margin-top: .5rem;
    font-size: .7rem;
}

button {
    display: block;
    width: fit-content;
    margin: auto;
    margin-top: 1rem;  
}

img {
    display: block;
    width: 350px;
    height: 200px;
    margin: auto;
    object-fit:cover;
    object-position: top;
}
#my_achivements {
    margin-bottom: 100px;
    margin-top:170px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-items: center;
}
@media (max-width: 600px) {
    #my_achivements{
        margin-top: 250px;
    }
}

</style>
