<template>
    <section class="dark_container" > 
        <Select @selected="filteredGenre"/>
        <div class="album" v-if="!loading">
            <div class="card_container"
            v-for="(card, index) in filterSearch" 
            :key="index">
                <Card :item="card" />
            </div> 
        </div>
        <Loading v-else />
    </section>
</template>

<script>
import Card from '../components/Card.vue';
import Loading from '../components/Loading.vue';
import Select from '../components/Select.vue' 
import axios from 'axios'; 

export default {
    name: "Cards",
    components: {
        Card, 
        Loading, 
        Select
    },
    data () {
        return {
            api: "https://flynn.boolean.careers/exercises/api/array/music", 
            cards: [], 
            loading: true,
            filterType: "" , 
            filterAuthor:"", 
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
                    }, 1000
                    )
                }
            )
    }, 
    methods : {
        filteredGenre(text) {
            this.filterType = text; 
        }, 
        filteredAuthor(text) {
            this.filterAuthor = text; 
        }
    }, 
    computed: {
        filterSearch() {
            const newArray = this.cards.filter(card =>
            {
                return card.genre.includes(this.filterType) || card.author.includes(this.filterType); 
            }
            )
            return newArray; 
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss'; 
    .dark_container {
        padding: 50px;
        padding: 20px 0;
        height: calc(100vh - 74px);
        overflow: hidden;
        background-color: $colorDarkGrey;
    }
    .album {
        width: 65%;
        height: 100%;
        margin: auto;
        display: flex;
        justify-content: space-evenly;
        flex-wrap: wrap;
        
    }
</style>