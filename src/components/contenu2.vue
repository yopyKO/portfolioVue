<template>
    <div class="container my-5">

    <h2 class="mb-5"></h2>

    <modale2 v-bind:revele="revele" v-bind:toggleModale="toggleModale"></modale2>
    <div v-on:click="toggleModale" class="btn btn-success" id="title">Plus de détails</div>

    </div>
</template>

<script>

import Modale2 from './modale2.vue'

export default {
        name: 'contenu',
        data(){
            return { 
                revele:false
            }
        },
        components:{
            'modale2': Modale2
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