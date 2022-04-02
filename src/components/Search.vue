<template>
  <input placeholder="Type something to search for awesome gifs" v-model="keyword" @input="onInput">
</template>

<script>

export default {
    name: 'SearchGif',
    data(){
        return {
            keyword: ' ',
            timeout: null,
        }
    },
    methods: {
        onInput() {
            clearTimeout(this.timeout);
           this.timeout = setTimeout(() => {
               this.search();
           }, 500);
        },
        search() {
             fetch('http://api.giphy.com/v1/gifs/search?api_key=NEvXSrnZlb34J8ZlpNHFgJSQzHrLoeQH&q=${this.keyword}&limit=9')
            .then(response => response.json())
            .then(result => {
            console.log(result);
            this.$emit('fetch-gifs', result.data);
            })
        }
    }

}
</script>

<style scoped>
    input {
        padding: 10px 16px;
        border-radius: 4px;
        font-size: 18px;
        outline: 0;
        display: block;
        border: 2px solid #5f5f5f;
        width: 100%;
    }
    input:focus {
        border-color: #02153d;
    }
</style>