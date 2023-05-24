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
      this.store.carte = risposta.data.data;
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
            <div v-for="dato in store.carte" class="box">
                <div class="boxImg">
                    <img v-if="dato.card_images[0]" :src="dato.card_images[0].image_url" alt="">
                </div>
                <div class="boxText">
                    <h3> {{ dato.name}} </h3>
                    <p> {{ dato.archetype }}</p>
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
    margin: 10px;
    background-color: $colore;
}

.boxImg{
    width: 100%;
}

.boxText{
    text-align: center;
    h3{
        padding: 1rem 0;
        color: white;
    }

    p{
        padding: 0.5rem 0;
    }
}

</style>