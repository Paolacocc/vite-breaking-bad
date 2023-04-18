<script>
import AppHeader from "./components/AppHeader.vue"
import AppMain from "./components/AppMain.vue"
import AppBtn from "./components/AppBtn.vue";
import axios from "axios";
import { store } from "./store.js";


export default {
  components: {
    AppHeader,
    AppMain,
    AppBtn
  },
  data(){
    return {
      store
    }
  },
  mounted() {
   this.getCards();
  },
  methods: {
    getCards(){
      this.store.loading = true;
      const params = {}
      if(this.store.statusArray) {
        params.archetype = this.store.statusArray;
      }
      axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0", { params: 
        {archetype: this.store.activeStatus
        },
      })
      .then((resp) => {
        this.store.cards = resp.data.data;
        console.log(this.store.cards);
      })


    },
    handleCall(){
      this.getCards();
    }
  }

}
</script>

<template>
  <AppHeader />
  <AppBtn @filter="handleCall"/>
  <AppMain />
</template>

<style lang="scss">
@use "./general.scss";
</style>