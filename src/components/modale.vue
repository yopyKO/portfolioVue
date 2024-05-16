<template>

    <div class="bloc-modale" v-if="revele">    
        <div class="overlay" v-on:click="toggleModale"></div>
        <div class="modale card">
            <div v-on:click="toggleModale" class="btn-modale btn btn-danger">X</div>
            <h2>Mon CV en Ligne</h2>
            <a href="https://github.com/yopyKO/CV_devoir" target="_blank">
                <img class="cvImg" src="../assets/cv.png" alt="Cv Grosbois Charly">
            </a>
            <p>Crée le 29 Février 2024 en Html, CSS</p>
        </div>      
    </div>
</template>

<script>
    export default{
        name: 'Modale',
        props: ['revele','toggleModale']
    }
</script>

<style scoped>
    h2{
        display: flex;
        justify-content: center;
        color:rgb(14, 88, 14);
        font-weight: 700;
    }
    .bloc-modale{
        position: fixed;
        display:flex;
        justify-content: center;
        align-items: center;
        top: 0;
        bottom: 0;
        left: 0;
        right:0 ;
        z-index: 102;
    }
    .overlay {
        background: rgba(0,0,0,0.5);
        position:fixed;
        top: 0;
        bottom: 0;
        left: 0;
        right:0 ;
    }
    .modale{
        background: linear-gradient(rgb(238, 248, 209), rgb(255, 255, 255));
        color:#333;
        padding:50px;
        position: fixed;
        border-radius:2%;
    }
    .modale-card{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-content: center
    }
    .btn-modale {
        position: absolute;
        top:10px;
        right:10px;
        background-color: rgb(216, 42, 42);
        color:white;
        width:1em;
        height:1em;
        display:flex;
        justify-content: center;
        align-items: center;
        border-radius: 15%;
    }
    .btn-modale:hover {
        cursor: pointer;
    }
    .cvImg{
        display: flex;
        justify-content: center;
        align-content: center;
        width: 220px;
        height: 330px;
    }
</style>