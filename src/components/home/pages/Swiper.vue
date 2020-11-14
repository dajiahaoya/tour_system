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
    data() {
      return {
        swiperList:[
            {
                id:'01',
                //如果想要使用本地图片，需要在路径前加require()
                imgUrl:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1179273312,1128108760&fm=26&gp=0.jpg'
            },
            {
                id:'02',
                imgUrl:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=3963799090,258929742&fm=26&gp=0.jpg'
            },
            {
                id:'03',
                imgUrl:'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=1479628401,160371731&fm=26&gp=0.jpg'
            },
            {
                id:'04',
                imgUrl:'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=2890167039,1473458738&fm=26&gp=0.jpg'
            },
            {
                id:'05',
                imgUrl:'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1386247554,3443797009&fm=26&gp=0.jpg'
            }
        ],
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
    }
    .header-swiper img{
        width: 100%;
        height: 4rem;
    }
</style>
<style>

</style>