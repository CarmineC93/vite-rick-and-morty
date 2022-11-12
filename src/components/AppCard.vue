<script>
export default {
    name: "AppCard",
    props: {
        character: Object,
    }
}
</script>

<template>
<div class="character-card text-center">
        <div class="pic">
            <img class="rounded-circle" :src="character.image" :alt="character.name">
        </div>
        <div class="text">
            <h5>{{ character.name }}</h5>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    h5{
        color: white;
    }
</style>