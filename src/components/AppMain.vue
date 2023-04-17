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
            <div class="card-area row row-col-6 g-3">
                <div class="col" v-for="card in store.cards" :key="card.id">
                    <AppCard :cards="card"/>
                </div>
            </div>


        </div>
    </main>
</template>

<style lang="scss" scoped>
main {
    height: calc(100vh - 80px);
    background-color: orange;

    .container {
        width: 80%;
        margin: 0 auto;

        .card-area {
            background-color: white;
            // debug
            height: 600px;

        }

    }

    ._ms-btn {
        background-color: white;
        padding: 5px;
    }
}
</style>