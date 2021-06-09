<template>
    <div class="card">
        <img :src="item.poster" alt="item.title">
        <h2>{{item.title}}</h2>
        <h3>{{item.author}}</h3>
        <h4>{{item.year}}</h4>
    </div>
</template>

<script>
export default {
    name: "Card", 
    props: ["item"]
}

</script>

<style lang="scss" scoped>
@import '../style/variables.scss';
    .card {
        width: 150px;
        background-color: $colorLightGrey;

        h2, h3, h4 {
            text-transform: uppercase;
            color: white;
        }
        h2 {
            font-size: 25px;
        }
        h3 {
            font-size: 15px;
        }
        h4 {
            font-size: 12px;
        }
    }
</style>