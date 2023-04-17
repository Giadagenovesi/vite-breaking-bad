<script>
import AppHeader from "./components/AppHeader.vue"
import CardsList from "./components/CardsList.vue"
import axios from "axios";

import {store} from "./store";

export default {
  components: {
    AppHeader,
    CardsList,
  },
  data() {
    return {
      store
    }
  },
  mounted() {
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0").then((resp) => {
    this.store.characters = resp.data.data; 
    const myData = resp.data.data;
    console.log(myData);
    })
  }
}
</script>

<template>
  <AppHeader title="Yu-Gi-Oh-Api"/>
  <CardsList />
</template>

<style lang="scss">
@use "./Styles/general.scss"
</style>