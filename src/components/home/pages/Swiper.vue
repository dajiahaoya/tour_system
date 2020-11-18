<template>
    <div class="header-swiper">
        <swiper ref="mySwiper" :options="swiperOptions">
            <swiper-slide v-for='item in swiperList' :key='item.id'>
                <img :src="item.imgUrl" alt="">
            </swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
          </swiper>
    </div>
</template>
<script>
export default {
    name: 'carrousel',
    props:['swiperList'],
    data() {
      return {
        swiperOptions: {
          pagination: {
            el: '.swiper-pagination'
          },
          loop:true,
          autoplay: true
        }
      }
    },
    computed: {
      swiper() {
        return this.$refs.mySwiper.swiper
      }
    },
    mounted() {
      // current swiper instance
      // 然后你就可以使用当前上下文内的swiper对象去做你想做的事了
      console.log('this is current swiper instance object', this.swiper)
      this.swiper.slideTo(1, 1000, true)
    }
  }
</script>
<style scoped>
    .header-swiper{
        background: #ccc;
        height: 0;
        padding-bottom: 4rem;
        overflow: hidden;
    }
    .header-swiper img{
        width: 100%;
        height: 4rem;
    }
</style>
<style>

</style>