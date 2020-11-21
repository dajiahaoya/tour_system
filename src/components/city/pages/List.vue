<template>
  <div ref='container' class="container">
    <div class="main">
      <!--hot-->
      <div class="hot">
        <div class="hot-title">
          热门城市
        </div>
        <ul class="hot-list">
          <li class="hot-item" v-for="item in hotCities" :key="item.id" @click='changeCityName(item.name)'>
            {{item.name}}
          </li>
        </ul>
      </div>
      <!--sort-->
      <div class="sort">
        <div class="sort-title">
          字母排序
        </div>
        <ul class="sort-list">
          <li class="sort-item" v-for="(item,key) in cities" :key="item.id" @click='changeSort(key)'>
            {{key}}
          </li>
        </ul>
      </div>
      <!--list-->
      <div class="list">
        <div v-for="(val,key) in cities" :ref="key">
          <div class="list-title">
            {{key}}
          </div>
          <ul class="list-msg">
            <li class="list-item" v-for="item in val" :key="item.id" @click='changeCityName(item.name)'>
              {{item.name}}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>


</template>
<script>
  import {mapMutations} from 'vuex'
  import BScroll from 'better-scroll'
  export default {
    props: ['hotCities', 'cities'],
    data() {
      return {
        scroll: ''
      }
    },
    mounted() {
      // console.log(this.$refs['container']);
      let container = this.$refs['.container'];
      this.$nextTick(() => {
        this.scroll = new BScroll(this.$refs.container, {
          click: true,
          mouseWheel: true
        });
      })
    },
    methods: {
      changeSort(sortName) {
        this.scroll.scrollToElement(this.$refs[sortName][0]);
        // console.log(this.$refs[sortName][0]);
        // console.log(this.$refs);
      },
      changeCityName(cityName) {
        this.changeCity(cityName);
        this.$router.push('/');
      },
      ...mapMutations(['changeCity'])
    }
  }

</script>
<style scoped lang="stylus">
  @import '~css/common.styl';

  .container {
    position: absolute;
    overflow: hidden;
    left: 0;
    right: 0;
    bottom: 0;
    top: .88rem;
  }

  .main {
    height: 250rem;
  }

  .hot-title {

    font-size: .24rem;
    background: #f5f5f5;
    padding: .2rem;
  }

  .hot-list {
    overflow: hidden;
    position: relative;
    font-size: .28rem;
    background: #fff;
    color: #212121;
  }

  .hot-list:before {
    content: " ";
    position: absolute;
    height: 100%;
    width: 33.3333%;
    left: 33.3333%;
    border-right: .02rem solid #ddd;
    border-left: .02rem solid #ddd;
  }

  .hot-item {
    position: relative;
    float: left;
    width: 33.33333%;
    text-align: center;
    height: .9rem;
    line-height: .9rem;
    border-bottom: .02rem solid #ddd;
  }

  .sort {
    font-size: .24rem;
    background: #f5f5f5;
  }

  .sort-title {
    padding: .2rem;
  }

  .sort-list {
    position: relative;
    overflow: hidden;
    font-size: .28rem;
    background: #fff;
    color: #212121;
    padding: .3rem 0;
  }

  .sort-item {
    text-align: center;
    height: .9rem;
    line-height: .9rem;
    width: 16.66666%;
    float: left;
  }

  .list {
    font-size: .24rem;
    background: #f5f5f5;
  }

  .list-title {
    padding: .2rem;
  }

  .list-msg {
    overflow: hidden;
    font-size: .28rem;
    background: #fff;
    color: #212121;
    position: relative;
  }

  .list-msg:before {
    content: " ";
    position: absolute;
    height: 100%;
    width: 25%;
    left: 25%;
    border-right: .02rem solid #ddd;
    border-left: .02rem solid #ddd;
  }

  .list-msg:after {
    content: " ";
    position: absolute;
    height: 100%;
    width: 0;
    left: 75%;
    border-left: .02rem solid #ddd;
  }

  .list-item {
    width: 25%;
    float: left;
    position: relative;
    text-align: center;
    line-height: .9rem;
    border-bottom: .02rem solid #ddd;
    textOverflow();
  }

</style>
