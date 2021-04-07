<template>
<div class="container">
    <div class="row">

        <div class="col-sm-6 col-md-4 col-lg-3 mb-4" v-for="character in characters" :key="character">
            <div class="card">
                <div class="card-body d-flex flex-column justify-content-between  characters-cards">
                    <h3>{{ character.name }}</h3>

                    <div class="btn-container">                
                        <router-link :to="{ name: 'Character', params: { id: character.id } }"> 

                            <button class="btn btn-dark">
                                Classified File
                            </button>

                        </router-link>
                    </div>

                </div>

            </div>

        </div>
    </div>
</div>
  
</template>

<script>

// import { public_key } from '../marvel.js'; //, secret_key
// import axios from 'axios';

import { mapState } from 'vuex'

export default {
    name: 'Characters',


    mounted(){

        this.$store.dispatch('getCharacters')
        console.log(this.characters);
    },

    computed: {

        ...mapState({
            characters: state => state.characters
        })
    },


    methods: {
    
    }

}
</script>

<style lang="scss">
    
</style>