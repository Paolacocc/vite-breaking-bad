<script>
import AppCard from './AppCard.vue';
import { store } from "../store"
export default {
    name: "AppMain",
    components: {
        AppCard
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
            <div class="dropdown">
                <button class="btn mt-4 mb-4 dropdown-toggle _ms-btn " type="button" id="dropdownMenuButton1"
                    data-bs-toggle="dropdown" aria-expanded="false">
                    Alien
                </button>
                <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
                    <li><a class="dropdown-item" href="#">Action</a></li>
                    <li><a class="dropdown-item" href="#">Another action</a></li>
                    <li><a class="dropdown-item" href="#">Something else here</a></li>
                </ul>
            </div>
            <div class="header-main">Found 20 cards</div>
            <div class="card-area m-0 p-2 row row-cols-5 g-3">
                
                <div class="col" v-for="card in store.cards" :key="card.id">
                    <AppCard :cards="card"/>
                </div>
            </div>


        </div>
    </main>
</template>

<style lang="scss" scoped>
@use "../styles/variables.scss" as *;
main {
    height: calc(100vh - 80px);
    background-color: $primary;
    .header-main {
        background-color: black;
        padding: 10px;
        color: white;

    }

    .container {
        flex-grow: 1;
        overflow-y: scroll;
        width: 80%;
       margin: 0 auto;

        .card-area {
            height: 100%;
            
            overflow-y: scroll;
            background-color: white;
           
        }

    }

    ._ms-btn {
        background-color: white;
        padding: 5px;
    }
}
</style>