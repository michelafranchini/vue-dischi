<template>
    <section class="dark_container" > 
        <div class="album" v-if="!loading">
            <div class="card_container"
            v-for="card in cards" 
            :key="card.id">
                <Card :item="card" />
            </div> 
        </div>
        <Loading v-else />
    </section>
</template>

<script>
import Card from '../components/Card.vue';
import Loading from '../components/Loading.vue'
import axios from 'axios'; 

export default {
    name: "Cards",
    components: {
        Card, 
        Loading
    },
    data () {
        return {
            api: "https://flynn.boolean.careers/exercises/api/array/music", 
            cards: [], 
            loading: true, 
        }
    }, 
    created() {
        axios
            .get(this.api)
            .then(
                (result) => {
                    // console.log(result.data);
                    this.cards = result.data.response; 

                    setTimeout( () => {
                        this.loading = false; 
                    }, 5000
                    )
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
        padding: 20px 0;
        height: 100vh;
    }
    .album {
        width: 62%;
        height: 100%;
        margin: auto;
        display: flex;
        flex-wrap: wrap;
        
    }
</style>