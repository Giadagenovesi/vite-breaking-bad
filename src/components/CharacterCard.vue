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
        <img :src="character.card_images[0].image_url_small" alt="">
        <div class="card-body">
            <h5 class="card-title">{{ character.name }}</h5>
            <p class="card-text"> {{ character.archetype }}</p>
        </div>
    </div>
</template>

<style scoped lang="scss">
.card {
    height: 100%;
}
.card-body {
    background-color:#D48F38;

    h5 {
        color: white;
    }

}
</style>