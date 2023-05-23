<script>
import { store } from '../data/store';
import axios from 'axios';

export default {
  data() {
    return {
        store
    }
  },
  mounted() {
    console.log("store", store)

    axios.get(this.store.urlAPI).then(risposta => {
      console.log(risposta.data.data);
      this.store = risposta.data.data;
      console.log(this.store)
    }).catch(error => {
      console.error("te pareva");
    })
  }
}
</script>

<template>
    <div class="containerMain">
        <div class="headMain">
            <p>Found 39 card</p>
        </div>

        <div class="containerBox">
            <div v-for="dati in store" class="box">
                <div class="boxImg">
                    <img :src="dati.card_images[0].image_url" alt="">
                </div>
                <div class="boxText">
                    <h3> {{ dati.name}} </h3>
                    <p> {{ dati.archetype }}</p>
                </div>
            </div>

        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables.scss' as *;

.containerMain{
    max-width: 1680px;
    background-color: white;
    padding: 70px;
}

.headMain{
    padding: 1rem;
    background-color: #222;
    color: white;
}

.containerBox{
    display: flex;
    flex-wrap: wrap;
}

img{
    width: 100%;
    display: block;
}

.box{
    width: calc(100% / 5 - 20px);
    height: 520px;
    margin: 10px;
    background-color: $colore;
}

.boxImg{
    width: 100%;
    height: 400px;
}

.boxText{
    text-align: center;
    h3{
        padding: 1rem 0;
        color: white;
    }
}

</style>