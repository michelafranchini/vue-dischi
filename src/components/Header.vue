<template>
  <div class="header_container">
      <img class="logo" src="../img/spotify.png" alt="logo">
  </div>
</template>

<script>
export default {
    name: "Header", 
}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss'; 

.header_container {
    background-color: $colorLightGrey;
    img {
        width: 50px;
        margin: 10px;
    }
}
</style>