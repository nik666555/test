<template>
  <div>
    <gallery :images="images" :index="index" @close="index = null"/>
    <div
      class="slider__image"
      v-for="(image, imageIndex) in images"
      :key="imageIndex"
      @click="index = imageIndex"
      :style="{ backgroundImage: 'url(' + image + ')' }"
    ></div>
  </div>
</template>
 
<script>
  import VueGallery from 'vue-gallery';
  import {images} from '../images.js';
  
  export default {
    name: 'TheSlider',
    data () {
      return {
        images: images,
        index: null
      };
    },
 
    components: {
      'gallery': VueGallery
    }
  }
</script> 
 
<style scoped lang="scss">
  .slider__image {
    float: left;
    position: relative;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center center;
    border-top: 1px solid #ffc64a;
    border-bottom: 1px solid #8c4f00;
    border-left: 1px solid #ca8f28;
    border-right: 1px solid #ca8f28;
    margin-right: 5px;
    width: 89px;
    height: 50px;
    cursor: pointer;
    &:last-child {
      margin-right: 0;
    }
  }
</style> 
 