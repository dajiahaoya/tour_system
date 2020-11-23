<template>
  <div class="banner">
    <div @click="handleClick">
      <div class="banner-img">
        <img src="http://img1.qunarzz.com/sight/p0/2008/b9/b9cc3ab2fbe4f0e7a3.water.jpg_600x330_41191030.jpg" alt="">
      </div>
    </div>
    <div class="banner-title">
      上海海昌海洋公園(AAAA景區)
    </div>
    <div class="img-swiper" v-show="imgSwiper" @click="hideSwiper" v-for="item in bannerList">
      <swiper ref="mySwiper" :options="swiperOptions">
        <swiper-slide v-for='item in bannerList' :key='item.id'>
          <img :src="item.imgUrl" alt="">
        </swiper-slide>
    </swiper>
    <div class="swiper-pagination" slot="pagination"></div>
    </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        swiperOptions: {
          pagination: {
            el: '.swiper-pagination',
            type:"fraction"
          },
          loop: true,
          autoplay: true
        },
        bannerList: [{
            "id": "01",
            "imgUrl": "http://img1.qunarzz.com/sight/p0/2008/b9/b9cc3ab2fbe4f0e7a3.water.jpg_600x330_41191030.jpg"
          },
          {
            "id": "02",
            "imgUrl": "http://img1.qunarzz.com/sight/p0/2008/e5/e5c01dfca72bc4dda3.water.jpg_350x240_c1b9b261.jpg"
          },
          {
            "id": "03",
            "imgUrl": "http://img1.qunarzz.com/sight/p0/2008/c4/c417d56ff1a4c0fea3.water.jpg_350x240_42071468.jpg"
          },
          {
            "id": "04",
            "imgUrl": "http://img1.qunarzz.com/sight/p0/2008/66/6670f95c09cff3a5a3.water.jpg_350x240_63b10ee0.jpg"
          }
        ],
        imgSwiper: false
      }
    },
    methods: {
      handleClick() {
        this.imgSwiper = true;
      },
      hideSwiper() {
        this.imgSwiper = false;
      }
    }
  }

</script>
<style scoped>
  .banner {
    position: relative;
  }

  .banner-img {
    width: 100%;
    overflow: hidden;
    height: 0;
    padding-bottom: 55%;
  }

  .banner-img img {
    width: 100%;
  }

  .banner-title {
    position: absolute;
    bottom: .3rem;
    left: .4rem;
    font-size: .36rem;
    color: #fff;
  }

  .img-swiper {
    background: #000;
    position: fixed;
    top: 0;
    bottom: 0;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .img-swiper img {
    width: 100%;
  }

  .swiper-pagination{
      color: #fff;
      font-size: .24rem;
      bottom: .3rem
  }

</style>
