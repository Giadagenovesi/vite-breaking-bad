<script>
export default {
    name: "CharacterCard",
    props: {
        character: Object
    }
}
</script>

<template>
    <div class="card">
        <img src="https://images.ygoprodeck.com/images/cards_small/34541863.jpg" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title">{{ character.name }}</h5>
            <p class="card-text"> {{ character.archetype }}</p>
        </div>
    </div>
</template>

<style scoped lang="scss">
.card-body {
    background-color:#D48F38;

    h5 {
        color: white;
    }

}
</style>