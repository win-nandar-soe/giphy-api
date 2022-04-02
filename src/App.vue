<template>
  <search @fetch-gifs="onFetch" />
  <gif-list :gifs="gifs"/>
</template>

<script>
import Search from "@/components/Search.vue";
import GifList from "@/components/GifList.vue";
export default {
  name: 'App',
  components: {
    Search,
    GifList
  },
  data() {
    return {
      gifs: []
    }
  },
  methods: {
    onFetch(result) {
      this.gifs= result;
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
</style>
