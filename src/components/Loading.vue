<template>
    <div class="loader">
        <h2>Aspetta solo qualche secondo</h2>
        <img src="../img/loading-pacman.svg" alt="">
        <h2>Tra poco potrai ascoltare la tua musica preferita senza attese</h2>
    </div>
</template>

<script>
export default {
    name: "Loading", 
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';
    .loader {
        position: fixed;
        top: 0;  
        left: 0; 
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column ;
        justify-content: center;
        align-items: center;
        background-color: $colorDarkGrey;

        h2{
            display: block;
            font-size: 30px;
            text-transform: uppercase;
            color: white; 
        }
    }
</style>