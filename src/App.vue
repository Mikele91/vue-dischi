<template>
    <div id="app">
      <Header @search ="searchAlbum"/>
      <Albums :music="selectMusic"/>
      

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
      selectMusic :""
      }
  },
  methods:{
        searchAlbum(text){

          this.selectMusic = text;
        }
    },
}
</script>

<style lang="scss">
@import './assets/style/common.scss';


</style>
