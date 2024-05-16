<template>
    <div class="container my-5">

    <h2 class="mb-5"></h2>

    <modale v-bind:revele="revele" v-bind:toggleModale="toggleModale"></modale>
    <div v-on:click="toggleModale" class="btn btn-success" id="title">Plus de détails</div>

    </div>
</template>

<script>

import Modale from './modale.vue'

export default {
        name: 'contenu',
        data(){
            return { 
                revele:false
            }
        },
        components:{
            'modale': Modale
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