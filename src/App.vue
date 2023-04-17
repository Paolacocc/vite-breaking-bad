<script>
import AppHeader from "./components/AppHeader.vue"
import AppMain from "./components/AppMain.vue"
import axios from "axios";
import { store } from "./store.js";

export default {
  components: {
    AppHeader,
    AppMain
  },
  data(){
    return {
      store
    }
  },
  mounted() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
      .then((resp) => {
        this.store.cards = resp.data.data;
        console.log(this.store.cards);
      })
  }

}
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss">
@use "./general.scss";
</style>