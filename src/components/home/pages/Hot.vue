<template>
    <div class="hot">
        <div class="hot-top">
            <img src="http://img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png" alt="">
            <span>本周热门榜单</span>
            <span class="hot-title">全部榜单 ></span>
        </div>
        <ul class="hot-list">
            <li class="hot-item" 
            v-for="item in hotList" 
            :key="item.id">
                <img :src="item.imgSrc" alt="">
                <p>{{item.title}}</p>
                <p>
                    <span class="hot-mark">¥{{item.mark}}</span>起
                </p>
            </li>
        </ul>
    </div>
</template>
<style scoped lang="stylus">
@import '~css/common.styl';
.hot{
    margin-top: .2rem;
    background: #fff;
    font-size: .28rem;
}
.hot-top{
    padding: .2rem;
    position: relative;
}
.hot-top img{
    width: .3rem;
    height: .3rem;
}
.hot-top span{
    color: #212121;
    font-size: .32rem;
}
.hot-top span.hot-title{
    position: absolute;
    right: .2rem;
    color: #616161;
    font-size: .28rem;
}
.hot-list{
    overflow-x: scroll;
    overflow-y: hidden;
    white-space: nowrap;
}
.hot-item{
    display: inline-block;
    padding: 0 .2rem;
    width: 2rem;
    height: 2rem;
}
.hot-item img{
    width: 100%;
    height: 100%;
}
.hot-item p{
    margin-top: .1rem;
    text-align: center;
    textOverflow();
}
.hot-item p .hot-mark{
    color: #ff8300;
    font-size: .32rem;
}
</style>
<script>
export default{
    data () {
        return{
            hotList:[
                {
                    id:'01',
                    imgSrc:'http://img1.qunarzz.com/sight/p0/2011/e6/e6568888096dd6f3a3.water.jpg_250x250_3e2b5647.jpg',
                    title:'长隆欢乐世界',
                    mark:'222'
                },
                {
                    id:'02',
                    imgSrc:'http://img1.qunarzz.com/sight/p0/2011/f0/f050f346cfd6dc62a3.water.jpg_250x250_92b836b3.jpg',
                    title:'长隆野生动物世界',
                    mark:'351'
                },
                {
                    id:'03',
                    imgSrc:'http://img1.qunarzz.com/sight/p0/1603/1c/1c67791edbe2677b90.img.jpg_250x250_8f1dcbbd.jpg',
                    title:'珠江夜景',
                    mark:'111'
                },
                {
                    id:'04',
                    imgSrc:'http://img1.qunarzz.com/sight/p0/1603/20/208ed6bc971a41cf90.img.jpg_250x250_d149a062.jpg',
                    title:'宝墨园',
                    mark:'222'
                },
                {
                    id:'05',
                    imgSrc:'http://img1.qunarzz.com/sight/p0/201309/06/a03726324b885c8bc8d65eac.jpg_250x250_468addc5.jpg',
                    title:'广州塔',
                    mark:'145'
                }
            ]
        }
    }
}
</script>