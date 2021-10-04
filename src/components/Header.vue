<template>
  <header>
        <img src="../assets/images/spotify-logo.png" alt="" class="m-2">
        <form class="mx-5">
        <label for="musical-genre">Choose a Genre:</label>
        <select @change="$emit('search', inputMusic)" v-model="inputMusic" name="musical-genre" id="musical-genre">
          <option  value="">ALL</option>
          <option v-for="(pluto,index) in ciccio" :key="index" :value="pluto">{{pluto}}</option>
        </select>

        </form>
  </header>
</template>

<script>
export default {
name: "Header",
data(){
  return{
    inputMusic:""
  }
},
props:{
  ciccio:Array
}
}
</script>

<style  lang="scss" scoped>
@import '../assets/style/variables.scss';
header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 6.25rem;
    background-color: $headerColor;
    select{
      min-width: 10rem;
      padding: .625rem;
    }
    img{
        height: 80%;
    };
    
}

</style>