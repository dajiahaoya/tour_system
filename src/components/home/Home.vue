<template>
  <div class="home">
    <home-header></home-header>
    <home-swiper :swiperList='swiperList'></home-swiper>
    <home-icons :iconsList='iconsList'></home-icons>
    <home-location></home-location>
    <home-activity></home-activity>
    <home-hot :hotList='hotList'></home-hot>
    <home-like :likeList='likeList'></home-like>
    <home-vacation :vacationList='vacationList'></home-vacation>
  </div>
</template>
<script>
  import {mapState} from 'vuex'
  import HomeHeader from './pages/Header'
  import HomeSwiper from './pages/Swiper'
  import HomeIcons from './pages/Icons'
  import HomeLocation from './pages/Location'
  import HomeActivity from './pages/Activity'
  import HomeHot from './pages/Hot'
  import HomeLike from './pages/Like'
  import HomeVacation from './pages/Vacation'
  export default {
    components: {
      HomeHeader,
      HomeSwiper,
      HomeIcons,
      HomeLocation,
      HomeActivity,
      HomeHot,
      HomeLike,
      HomeVacation
    },
    data() {
      return {
        swiperList: [],
        iconsList: [],
        hotList: [],
        likeList: [],
        vacationList: [],
        changeCity:''
      }
    },
    computed: {
      ...mapState(['city'])
    },
    methods: {
      getHttp() {
        this.$http.get("/api/dataHome.json")
          .then((res) => {
              const data = res.data.data;
            //   console.log(typeof data);
            // for((item, index) in data){
                
            // }
            // console.log(typeof data);
            data.forEach((item, index) => {
              if (item.city == this.city) {
                // const data = res.data.data[0];
                this.swiperList = item.swiperList;
                this.iconsList = item.iconsList;
                this.hotList = item.hotList;
                this.likeList = item.likeList;
                this.vacationList = item.vacationList;
              }
            })
          })
      }
    },
    mounted() {
      // 两种请求方法
      // this.$http({
      //     url: "http://localhost:8080/static/mock/dataHome.json",
      //     method: "get",
      //     params: {}
      //     }).then(res => {
      //         const data = res.data.data[0];
      //         this.swiperList = data.swiperList;
      //         this.iconsList = data.iconsList;
      //         this.hotList = data.hotList;
      //         this.likeList = data.likeList;
      //         this.vacationList = data.vacationList;
      // })
      this.changeCity = this.city
      this.getHttp()
    },
    activated(){
        if(this.city!=this.changeCity){
            this.getHttp();
            this.city = this.changeCity;
        }
    }
  }

</script>
<style>
  .home {
    background: #f5f5f5;
  }

</style>
