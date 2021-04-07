<template>
    <div class="container">


        <div class="row">

            <div class="col-12 col-sm-6">
                <div class="card">
                    <div class="card-body">
                        <div v-for="char in character" :key="char">
                            <h3>{{ char.name }}</h3>
                            <p>{{ char.description }}</p>
                        </div>

                    </div>
                </div>
            </div>

            <div class="col-12 col-sm-6">
                <div cass="card">
                    <img :src="url" alt="" class="char-img">
                </div>
                
            </div>

        </div>

        <div class="btn-container">                
            <router-link to="/"> 

                <button class="btn btn-dark">
                    Back
                </button>

            </router-link>
        </div>



    </div>
</template>

<script>
// import {public_key} from '../marvel'
// import axios from 'axios'

import { mapState } from 'vuex'

export default {
    
    name: 'Character',

    data(){
        
        return{
            url: '',
            size: 'portrait_incredible.jpg',

        }
    },

    mounted(){

        this.$store.dispatch('getCharacter', this.$route.params.id);
        console.log(this.character);

        this.getImage()
    },

    computed: {

        ...mapState({
            character: state => state.character,
            preUrl: state => state.url
        })
    },


    methods: {
        getImage: function() {

            this.url = `${this.preUrl}${this.size}`
        }

    }
    
}
</script>

<style lang="scss">
    
</style>