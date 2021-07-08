<template>
  <main>
        <div class="container-lg">

            <div class="row">

                <div class="col-12 d-flex flex-wrap py-5">
                 

                    <div v-for="(element, index) in brani" :key="index" class="card bg-dark text-light" style="width: 12rem;" >
                        <img :src="element.poster" class="card-img-top" alt="...">
                        <div class="card-body">
                            <h5 class="card-title">{{element.title}}</h5>
                            <p class="card-text">{{element.author}}</p>
                            <p class="card-text">{{element.year}}</p>
                        </div>
                    </div>

                    


                </div>
            </div>
            
        </div>
  </main>
</template>

<script>
import axios from 'axios';

export default {
    name: "Main",
    data() {
        return {
            apiURL : 'https://flynn.boolean.careers/exercises/api/array/music',
            brani: [],
            // loading: true
        }

    },
    created(){
        this.getSong();
    },

    methods: {
        getSong(){
            axios
            .get(this.apiURL)
            .then (picker =>{
                // console.log(picker);
                this.brani = picker.data.response
                console.log(this.brani);
            })
        }
    }

}
</script>

<style scoped lang="scss">
    main{
        background-color: #1e2d3b;
        height: 1000px;
        .row{
            .col-12{
                .card{
                    width: calc(100% / 5);
                    margin: 20px;
                }
            }
        }
    }
</style>