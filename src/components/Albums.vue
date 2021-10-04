<template>
<div class="container my-5"> 
    <div class="row row-cols-5">
        <div class="col mb-3" v-for= "(elm, index) in musicFiltered" :key="index"> 
            <Album :info="elm" />
        </div>
        
    </div>
    

</div>
</template>

<script>
import axios from 'axios';
import Album from './Album.vue'

export default { 
    name: "Albums",
    components: {
        Album,
    },
    data(){
        return{
            album:[],
            genreAlbum:[],
        }
    },
    props:{
        music:String},
    computed:{
            musicFiltered(){
                    if(this.music!=""){
                        return this.album.filter(elm=> 
                        elm.genre == this.music
                    )    
                    }
                    return this.album

            }
    },
    // chimata al server tramite axios 
    created(){
        axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then( (res)=> {
            this.album= res.data.response ;   
            this.album.forEach(elm => {
                if(! this.genreAlbum.includes(elm.genre)){
                    this.genreAlbum.push(elm.genre)
                }
            });
            this.$emit("addGenre",this.genreAlbum )
        })
    }
}
</script>

<style  lang="scss" scoped>
.container{
    max-width: 75rem;
}

</style>