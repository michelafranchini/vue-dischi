<template>
    <div class="loader">
        <img src="../img/loading-pacman.svg" alt="">
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
    }
</style>