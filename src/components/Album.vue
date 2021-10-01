<template>
      <div class="album text-center">
        <img class="py-3" :src= "info.poster" alt="info.title">
        <h3>{{info.title}}</h3>
        <div>{{info.author}}</div>
        <div>{{info.year}}</div>
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
    height: 300px;
}
img{
    max-width: 60%;
}

</style>