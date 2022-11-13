<script>
    import { store } from "../store";

    export default {
        name: "ChangePage",
        data() {
        return {
            store,
            
            }
        }
    }
</script>

<template>
    <div>
        <span @click="$emit('changeLeft')"> PREV </span>
        <span @click="$emit('changeRight')"> NEXT </span>
    </div>
</template>

<style lang="scss" scoped>

div{
    display: flex;
    justify-content: space-between;
    align-items: center;

    span{
        height: 50px;
        width: 50px;
        border-radius: 50%;
        background-image: linear-gradient(rgb(89, 180, 50),rgb(92, 246, 21), rgb(22, 185, 190));
        margin: 0 2rem;
        line-height: 50px;
        text-align: center;
        font-weight: 600;
        color: rgb(11, 49, 82);

    }

    span:hover {
        box-shadow: 0px 0px 70px 24px #32e804;
        color: white;
    }
}
</style>