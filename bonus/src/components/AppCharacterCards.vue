<script>
import { store } from '../store.js'
export default {
    data() {
        return {
            store
        }
    },
    props:{
        myPokemon: Object
    },
    
    computed:{
        colorCard() {
            return store.colorMap[this.myPokemon.type1]
        }
    }

}
</script>
<template>
    <div class="d-flex align-items-center m-2 space card" :style="{'background-color': colorCard}">
        <img :src="myPokemon.imageUrl" :alt="myPokemon.name">
        <div>{{ myPokemon.number }}</div>
        <p><strong>{{ myPokemon.name }}</strong></p>
        <div>{{ myPokemon.type1 }}</div>
    </div>
</template>
<style lang="scss" scoped>
    img{
        width: 120px;
        height: 120px;
        border-radius: 50%;
    }

    .space{
        padding: 10px 20px;
    }

    .grass-bg{
        background-color: #26c281 !important;
    }

    .water-bg{
        background-color: #89c4f4 !important;
    }

    .fire-bg{
        background-color: #f47983 !important;
    }
</style>