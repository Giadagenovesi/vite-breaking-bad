<script>
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
}
</script>

<template>
    <main>
        <div class="ms-sort-container py-4">
            <SortCard />
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