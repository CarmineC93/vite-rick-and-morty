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
    <div class="container flex">
        <div class="grid justify-between">
            <div class="row row-cols-5 m-2 g-3">
                <div class="col" v-for="character in store.characters" :key="character.id">
                    <AppCard :character="character" />
                </div>
            </div>
        </div>    
    </div>

</template>

<style lang="scss" scoped>
    .container{

        background-image: linear-gradient(to left, 
        rgba(82, 11, 154, 0.389), rgba(16, 170, 19, 0.389) , rgba(26, 131, 145, 0.389));

        border-radius: 20px;
    }
</style>