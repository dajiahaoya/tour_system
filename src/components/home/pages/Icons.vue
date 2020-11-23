<template>
  <div class="icons">
    <swiper ref="mySwiper" :options="swiperOptions">
      <swiper-slide v-for="(item,key) in page" :key="key">
        <div class="icons-item" v-for="page in item" :key="page.id">
          <img :src="page.imgUrl" alt="">
          <p>{{page.title}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
  export default {
    props: ['iconsList'],
    data() {
      return {
        swiperOptions: {
          pagination: {
            el: '.swiper-pagination'
          }
        },
      }
    },
    computed: {
      page() {
        let pages = [];
        // console.log(this.iconsList);
        // for((item,index) in iconsList){
        //     let idx = Math.floor(index/8);
        //     if(!pages[idx])pages[idx] = [];
        //     pages[idx].push(item)
        // }
        if (this.iconsList) {
          this.iconsList.forEach((item, index) => {
            let idx = Math.floor(index / 8);
            if (!pages[idx]) pages[idx] = [];
            pages[idx].push(item)
          })
          return pages;
          // console.log(typeof pages);
        }
      }
    }
  }

</script>
<style scoped lang="stylus">
  @import '~css/common.styl';

  .icons {
    width: 100%;
    overflow: hidden;
    background: #fff;
    overflow: hidden;
  }

  .icons-item {
    width: 25%;
    height: 25%;
    float: left;
    margin-bottom: .2rem;
  }

  .icons-item img {
    width: 1.1rem;
    height: 1.1rem;
    display: block;
    margin: 0 auto;
    padding-top: .2rem;
  }

  .icons-item p {
    margin-top: .1rem;
    font-size: .28rem;
    text-align: center;
    color: #212121;
    textOverflow();
  }

  .swiper-pagination {
    bottom: 0;
  }

</style>
