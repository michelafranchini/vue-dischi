<template>
    <section class="dark_container"> 
          
        <div class="card_container"
        v-for="card in cards" 
        :key="card.id">
            <Card :item="card" />
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
        background-color: $colorDarkGrey;
    }
    .card_container {
        width: 70%;
        margin: auto;
        display: flex;
        justify-content: space-evenly;
    }
</style>