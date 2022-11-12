<script>
    import { store } from "../store";
    import AppCard from "./AppCard.vue";

export default {
    name: "AppGrid",
    components:{
        AppCard
    },
    data() {
        return {
            store,
        }
    }

}
</script>

<template>
    <div class="container">
        <div class="grid">
            <div class="row row-cols-5 m-2 g-3">
                <div class="col" v-for="character in store.characters" :key="character.id">
                    <AppCard :character="character" />
                </div>
            </div>
        </div>    
    </div>

</template>

<style lang="scss" scoped>
    
</style>