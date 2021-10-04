<template>
<div class="container my-5"> 
    <div class="row row-cols-5">
        <div class="col mb-3" v-for= "(elm, index) in album" :key="index"> 
            <Album :info="elm" />
            <!-- <Header @search ="searchAlbum"/> -->
        </div>
        
    </div>
    

</div>
</template>

<script>
import axios from 'axios';
import Album from './Album.vue'
// import Header from './Header.vue'
export default { 
    name: "Albums",
    components: {
        Album,
        // Header,
    },
    data(){
        return{
            album:[]
        }
    },
    // methods:{
    //     searchAlbum(text){

    //         console.log(text);
    //     }
    // },
    // chimata al server tramite axios 
    created(){
        axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then( (res)=> {
            this.album= res.data.response ;
        })
    }
}
</script>

<style  lang="scss" scoped>
.container{
    max-width: 75rem;
}

</style>