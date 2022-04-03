<template>
  <searchGif @fetch-gifs="onFetch" />

  <gif-list :gifs="gifs"/>
</template>

<script>
import SearchGif from "@/components/SearchGif.vue";
import GifList from "@/components/GifList.vue";
export default {
  name: 'App',
  components: {
    SearchGif,
    GifList
  },
  data() {
    return {
      gifs: [],
    }
  },
  methods: {
    onFetch(result) {
      console.log(result);
      this.gifs= result.data;
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  padding: 50px;
}
#app {
  width: 800px;
  margin: 0 auto;
}
</style>
