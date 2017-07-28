<template lang="pug">
  .col-sm-2.artist.col-xs-6
    a(:href="artist.url" target="_blank"  ) 
    img.img-thumbnail(:src="artist.image[2]['#text']" @click="master")
    .caption {{ artist.name | rinengan }}
</template>

<script>
var $ = require('jquery');
export default {
  name: 'artist',
  props: [ 'artist' ],
  methods:{
    master (){
      console.log("hiii");
      $("#myModal").modal("toggle");
    },    
  },
  filters:{
    rinengan (str){
      return str.toUpperCase();
    }
  }
}
</script>

<style lang="stylus" scoped>
li.artist
  display block
  margin 10px 0
</style>
