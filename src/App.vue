<template>
    <div id="app">
      <Header @search ="searchAlbum" :ciccio ="pippo"/>
      <Albums :music="selectMusic" @addGenre="saveArrey"/>
      

    </div>
</template>

<script>
import Albums from './components/Albums.vue'
import Header from './components/Header.vue'



export default {
  name: 'App',
  components: {
    Header,
    Albums,
    
  },
  data(){
    return {
      selectMusic :"",
      pippo:[],
      }
  },
  methods:{
        searchAlbum(text){

          this.selectMusic = text;
        },
        saveArrey(genreArrey){
          this.pippo = genreArrey

        }

    },
}
</script>

<style lang="scss">
@import './assets/style/common.scss';


</style>
