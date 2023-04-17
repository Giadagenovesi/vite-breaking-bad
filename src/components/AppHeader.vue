<script>
export default {
    name: "AppHeader",
    props: {
        title: String
    }
}
</script>

<template>
<header>
    <h1>
        {{ title }}
    </h1>
</header>
</template>

<style scoped lang="scss">
header {
    height: 80px;
    padding: 1rem;
}

</style>