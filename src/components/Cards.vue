<template>
    <section class="dark_container"> 
        <div class="album">
            <div class="card_container"
            v-for="card in cards" 
            :key="card.id">
                <Card :item="card" />
            </div> 
        </div>
      
    </section>
</template>

<script>
import Card from '../components/Card.vue';
import axios from 'axios'; 

export default {
    name: "Cards",
    components: {
        Card
    },
    data () {
        return {
            api: "https://flynn.boolean.careers/exercises/api/array/music", 
            cards: [], 
        }
    }, 
    created() {
        axios
            .get(this.api)
            .then(
                (result) => {
                    // console.log(result.data);
                    this.cards = result.data.response; 
                }
            )
    }
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss'; 
    .dark_container {
        padding: 50px;
        background-color: $colorDarkGrey;
    }
    .album {
        width: 70%;
        margin: auto;
        height: 100%;
        display: flex;
        flex-wrap: wrap;
        
    }
</style>