<template>
   <div id="gifLIst">
        <gifOne v-for="gif in gifs"  :key="gif.id"  :gif="gif" />
   </div>
   
</template>

<script>
import GifOne from "@/components/GifOne.vue";
export default {
    name: 'GifList',
    props: ['gifs'],
    components: {
        GifOne
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

