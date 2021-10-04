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
        }
    },
    props:{
        music:String},
    computed:{
            musicFiltered(){
                    if(this.music!=""){
                        return this.album.filter(elm=> 
                        elm.genre.toLowerCase() == this.music
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
        })
    }
}
</script>

<style  lang="scss" scoped>
.container{
    max-width: 75rem;
}

</style>