<script>
import AppCard from './AppCard.vue';
import { store } from "../store"
import AppLoading from "./AppLoading.vue"
export default {
    name: "AppMain",
    components: {
        AppCard,
        AppLoading
    },
    data(){
        return  {
            store
        }
    }
}
</script>

<template>
    <main>
        <div class="container">
      
            <div class="header-main">Found 20 cards</div>
            <AppLoading v-if="store.loading"/>
            <div class="card-area m-0 p-2 row row-cols-5 g-3" v-else>
                
                <div class="col _ms-col" v-for="card in store.cards" :key="card.id">
                    <AppCard :cards="card"/>
                   

                </div>
            </div>


        </div>
    </main>
</template>

<style lang="scss" scoped>
@use "../styles/variables.scss" as *;
main {
    height: calc(100% - 80px);
    background-color: $primary;
    
    .header-main {
        background-color: black;
        padding: 10px;
        color: white;

    }

    .container {
        
        width: 80%;
       margin: 0 auto;

        .card-area {
            height: 100%;
            flex-grow: 1;
            background-color: white;
            
            ._ms-col {
                overflow-y: scroll;
            }
           
        }

    }

    ._ms-btn {
        background-color: white;
        padding: 5px;
    }
}
</style>