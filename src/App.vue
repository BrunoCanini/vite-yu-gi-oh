<script>
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'

import { store } from './data/store';
import axios from 'axios';

export default {
  name: "App",
  components:{
    AppHeader,
    AppMain
  },
  data() {
    return {
      store
    }
  },
  mounted() {
    console.log("store", store)

    axios.get(this.store.urlAPI).then(risposta => {
      console.log(risposta)
    })
  }
}
</script>

<template>
  <AppHeader />
  <main>
    <select name="" id="">
      <option value="">Alien</option>
    </select>
    <AppMain />
  </main>
</template>

<style lang="scss" scoped>
@use './styles/partials/variables.scss' as *;

main{
  padding: 0 160px;
  background-color: $colore;
}

select{
  width: 140px;
  padding: 0.5rem;
  margin: 1rem 0;
}

</style>
