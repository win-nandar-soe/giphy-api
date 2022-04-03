<template>
<div class="gif"   :style="` background-image: url ('${gif.images.fixed_width.url}')` "></div>
<input type="text" ref="url" :value="gif.images.original.url" style="flex: 1">
<button @click="copyUrl()">Copy</button>
</template>

<script>
export default {
    name: 'GifOne',
    props: ['gif'],
    methods: {
        copyUrl() {
            this.$refs.url.select();
            this.$refs.url.setSelectionRange(0, 99999); /*For mobile devices*/
            document.execCommand("copy");
             this.$refs.url.value = 'Copied!!!';
        }
    }
}
</script>

<style scoped>
    .gif {
        width: 240px;
  height: 240px;
  margin-bottom: 20px;
  display: inline-flex;
  justify-content: center;
  align-items: flex-end;
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
    }

</style>