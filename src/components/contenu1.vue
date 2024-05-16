<template>
    <div class="container my-5">

    <h2 class="mb-5"></h2>

    <modale1 v-bind:revele="revele" v-bind:toggleModale="toggleModale"></modale1>
    <div v-on:click="toggleModale" class="btn btn-success" id="title">Plus de détails</div>

    </div>
</template>

<script>

import Modale1 from './modale1.vue'

export default {
        name: 'contenu',
        data(){
            return { 
                revele:false
            }
        },
        components:{
            'modale1': Modale1
        },
        methods:{
            toggleModale: function () {
                this.revele = !this.revele
            }
        }
    }
</script>

<style>
    .btn btn-success{
        border: 1px;
    }
    #title:hover{
        text-decoration: underline;
        cursor: zoom-in;
    }
</style>