<template>
  <header class="">
       <img src="../assets/images/spotify-logo.png" alt="" class="m-2">
  </header>
</template>

<script>
export default {
name: "Header"

}
</script>

<style  lang="scss" scoped>
@import '../assets/style/variables.scss';
header{
    height: 6.25rem;
    background-color: $headerColor;
    img{
        height: 80%;
    }
}

</style>