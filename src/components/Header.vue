<template>
  <header>
        <img src="../assets/images/spotify-logo.png" alt="" class="m-2">
        <form class="mx-5">
        <label for="musical-genre">Choose a Genre:</label>
        <select v-model="inputMusic" name="musical-genre" id="musical-genre">
          <option value="">ALL</option>
          <option value="jazz">Jazz</option>
          <option value="pop">Pop</option>
          <option value="rock">Rock</option>
          <option value="metal">Metal</option>
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