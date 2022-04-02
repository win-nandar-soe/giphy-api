<template>
   <div id="gifLIst">
        <gif v-for="gif in gifs"  :key="gif.id"  :gif="gif" />
   </div>
   
</template>

<script>
import Gif from "@/components/Gif.vue";
export default {
    name: 'GifList',
    props: {
        gifs : Array
    },
    components: {
        Gif
    }
}
</script>

<style  scoped>
    #gifList {
        margin-top: 20px;
        display: flex;
        flex-wrap: warp;
        justify-content: space-between;
        
    }
</style>>

