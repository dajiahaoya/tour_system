<template>
    <div class="header-swiper">
        <swiper ref="mySwiper" :options="swiperOptions">
            <swiper-slide>
                <img src="https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1179273312,1128108760&fm=26&gp=0.jpg" alt="">
            </swiper-slide>
            <swiper-slide>
                <img src="https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3963799090,258929742&fm=26&gp=0.jpg" alt="">
            </swiper-slide>
            <swiper-slide>
                <img src="https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=1479628401,160371731&fm=26&gp=0.jpg" alt="">
            </swiper-slide>
            <swiper-slide>
                <img src="https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=2890167039,1473458738&fm=26&gp=0.jpg" alt="">
            </swiper-slide>
            <swiper-slide>
                <img src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1386247554,3443797009&fm=26&gp=0.jpg" alt="">
            </swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
          </swiper>
    </div>
</template>
<script>
export default {
    name: 'carrousel',
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
        width: 100%;
        height: 2rem;
    }
    .header-swiper img{
        width: 100%;
        height: 4rem;
    }
</style>
<style>

</style>