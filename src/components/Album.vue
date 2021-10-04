<template>
      <div class="album text-center">
        
        <div class="container">

        <img class="py-3 " :src= "info.poster" alt="info.title">
        <h3>{{info.title}}</h3>
        <div class="text_author">{{info.author}}</div>
        <div>{{info.year}}</div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Album",
    props:{
        info: Object
    }

}
</script>

<style lang="scss" scoped>
@import '../assets/style/variables.scss';

.album{
    background-color: $headerColor;
    height: 350px;
    color: white;
    h3{
        font-size: 30px;

    }
}
img{
    max-width: 150px;
    height: 180px;
}

</style>