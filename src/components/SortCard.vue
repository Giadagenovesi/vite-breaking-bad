<script>
import {store} from '../store';
export default {
    name: "SortCard",
    emits: ["sorted"],
    data() {
        return {
            store,
            archetypeOption : ["Alien", "Ally of Justice", "Ancient Gear" ]
        }
    }
}
</script>

<template>
    <div class="sort-wrapper">
        <select class="form-select w-25" name="archetype" id="archetype" @change="$emit('sorted')" v-model="store.selectedArchetype">
            <option value="">All</option>
            <option :value="archetype" value="" v-for="archetype in archetypeOption">{{ archetype }} </option>
        </select>
    </div>
</template>

<style scoped lang="scss">

.sort-wrapper {
    width: 65%;
    margin: 0 auto;
}
</style>