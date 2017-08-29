<template>
  <swiper :options="swiperOption">
    <swiper-slide class="text">
      <slot></slot>
    </swiper-slide>
  </swiper>
</template>

<script>
  import {
    swiper,
    swiperSlide
  } from 'vue-awesome-swiper'
  export default {
    data() {
      let _this=this;
      return {
        swiperOption: {
          direction: 'vertical',
          slidesPerView: 'auto',
          mousewheelControl: true,
          freeMode: true,
          onTouchEnd(swiper){
               if(swiper.translate>200){
                //  console.log(this)
                   _this.$emit('pulldown');
               }
          }
        }
      }
    },
    methods:{
      getNewData(){
        alert(33333)
      }  
    },
    components: {
      swiper,
      swiperSlide
    }
  }
</script>

<style >
.swiper-slide.text {
  height:auto;
}
</style>