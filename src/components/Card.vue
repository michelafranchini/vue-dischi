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
        max-width: 200px;
        height: 350px;
        text-align: center;
        padding: 25px;
        margin: 10px;
        background-color: $colorLightGrey;

        img {
            width: 150px;
            margin-bottom: 10px;
        }

        h3, h4 {
            text-transform: uppercase;
            margin-bottom: 10px;
            color: #808080;
        }
        h2 {
            text-transform: uppercase;
            margin-bottom: 10px;
            font-size: 20px;
            color: white;
        }
        h3 {
            font-size: 15px;
        }
        h4 {
            font-size: 12px;
        }
    }
</style>