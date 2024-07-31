<template>
    <div class="banner">
        <swiper
            :space-between="30"
            :effect="'fade'"
            :autoplay="{
                delay: 1000000,
                disableOnInteraction: false,
            }"
            :loop="true"
            :modules="modules"
            class="banner"
        >
            <swiper-slide v-for="(item, index) in swiperList" :key="index">
                <div class="slide-bg" :style="{backgroundImage:'url('+item.img+')'}">
                    <div class="leftEgg">
                        <img :src="item.leftEgg" alt="">
                    </div>
                    <div class="rightEgg">
                        <img :src="item.rightEgg" alt="">
                    </div>
                </div> 
            </swiper-slide>
        </swiper>
        <div class="eggsList">
            <img v-for="(item) in eggsList" :key="item" class="`egg egg${}`" :src="item" alt="">
        </div>
        <div class="bottomHide" :style="{backgroundImage:'url('+bottomHideImg+')'}"></div> 
    </div>
</template>
<script>
// Import Swiper Vue.js components
import {
  Swiper, SwiperSlide
} from 'swiper/vue'

// Import Swiper styles
import 'swiper/css'

import 'swiper/css/effect-fade'
import 'swiper/css/navigation'
import 'swiper/css/pagination'

// import './style.css'

// import required modules
import {
  EffectFade, Navigation, Pagination, Autoplay
} from 'swiper/modules'

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [EffectFade, Navigation, Pagination, Autoplay],
    }
  },
  data() {
    return {
      swiperList: [{
        img: require('@/assets/images/home/banner/visual_1-pc.webp'),
        leftEgg: require('@/assets/images/home/banner/visual_1_illust_1.png'),
        rightEgg: require('@/assets/images/home/banner/visual_1_illust_2.png'),
      }, {
        img: require('@/assets/images/home/banner/visual_1-pc.webp'),
        leftEgg: require('@/assets/images/home/banner/visual_2_illust_1.png'),
        rightEgg: require('@/assets/images/home/banner/visual_2_illust_2.png'),
      }, {
        img: require('@/assets/images/home/banner/visual_1-pc.webp'),
        leftEgg: require('@/assets/images/home/banner/visual_3_illust_1.png'),
        rightEgg: require('@/assets/images/home/banner/visual_3_illust_2.png'),
      }],
      bottomHideImg: require('@/assets/images/home/banner/small_texture-white.png'),
      eggsList: [
        require('@/assets/images/home/banner/visual_illust_1.png'),
        require('@/assets/images/home/banner/visual_illust_2.png'),
        require('@/assets/images/home/banner/visual_illust_3.png'),
        require('@/assets/images/home/banner/visual_illust_4.png'),
        require('@/assets/images/home/banner/visual_illust_5.png'),
        require('@/assets/images/home/banner/visual_illust_6.png'),
        require('@/assets/images/home/banner/visual_illust_7.png'),
        require('@/assets/images/home/banner/visual_illust_8.png'),
      ],
    }
    
  },
}
</script>

<style lang="sass">
.banner
  width: 100%
  height: 90vh
  // margin-bottom: 8.3rem
  position: relative
  .swiper
    .slide
      width: 100%
      height: 100vh
    .swiper-slide 
      height: 100vh
      position: relative
      .slide-bg 
        background-size: cover
        background-position: center
        height: 90%
      .leftEgg, .rightEgg
        position: absolute
        width: 18vw
        max-width: 200px
        top: 45%
        img
          width: 100%
      .leftEgg
        left: 5%
        animation: egg-rotate1 3.5s steps(1) infinite
      .rightEgg
        right: 5%
        animation: egg-rotate2 3.5s steps(1) infinite

  .bottomHide
    width: 100%
    height: 60px
    position: absolute
    bottom: -1rem
    z-index: 1
    background-repeat: repeat-x
    transform: scale(1,-1)
    background-position: 50% 100%

@keyframes egg-rotate1
  0%, 100%
    transform: rotate(.00001deg) translateY(-50%)
  50%
    transform: rotate(20deg) translateY(-50%)

@keyframes egg-rotate2
  0%, 100%
    transform: rotate(.00001deg) translateY(-50%)
  50%
    transform: rotate(-20deg) translateY(-50%)
        
    
  

// nav
//   padding: 30px
//   a
//     font-weight: bold
//     color: #2c3e50
//     &.router-link-exact-active
//       color: #42b983
</style>

