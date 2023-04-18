<script>
import axios from 'axios';
import { store } from '../store';
import CharacterCard from './CharacterCard.vue';
import SortCard from './SortCard.vue';
export default {
    name: "CardsList",
    components: {
    CharacterCard,
    SortCard
},
    data() {
        return {
            store
        };
    },
    methods: {
        handleSorting () {
            axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0", {
                params: {
                    archetype: this.store.selectedArchetype,
                }
            }).then((resp) => {
                this.store.characters = resp.data.data;
            })
        }
    }

}
</script>

<template>
    <main>
        <div class="ms-sort-container py-4">
            <SortCard @sorted="handleSorting"/>
        </div>
        <div class="container py-4">
            <div class="ms-card-list-title py-3">
                <h4>Found 20 cards</h4>
            </div>
            <div class="ms-container">
                <div class="container-fluid py-4">
                    <div class="row row-cols-5">
                        <div class="col mb-4" v-for="character in store.characters" :key="character.id">
                            <CharacterCard :character="character"/>
                        </div>
                    </div>
                </div>   
            </div>
        </div>
    </main>
</template>

<style scoped lang="scss">
main {
    background-color:#D48F38;
    padding: 2rem;
}
.container {
    background-color: white;
}
.ms-card-list-title {
    width: 90%;
    margin: 0 auto;
    background-color: #212529;
    color: white;
    h4 {
        margin-left: 1rem;
    }
}
.ms-container {
    width: 90%;
    margin: 0 auto;
}
</style>