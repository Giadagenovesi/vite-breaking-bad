<script>
export default {
    name: "SortCard",
    data() {
        return {
            archetypeOption : ["Alien", "Ally of Justice", "Ancient Gear" ]
        }
    }
}
</script>

<template>
    <div class="sort-wrapper">
        <select class="form-select w-25" name="archetype" id="archetype">
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