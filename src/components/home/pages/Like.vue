<template>
    <div class="like">
        <div class="like-top">
            <img src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="">
            猜你喜欢
        </div>
        <ul>
            <li class="like-item border-bottom" v-for="item in Likelist">
                <div class="like-img">
                    <img :src="item.imgUrl" alt="">
                </div>
                <div class="like-text">
                    <div class="like-title">
                        {{item.title}}
                    </div>
                    <div class="like-message">
                        {{item.num}}条评论
                    </div>
                    <div class="like-map">
                        <span class="iconfont">&#xe870;&#xe870;&#xe870;&#xe870;&#xe870;</span>
                        <span class="like-mark">¥<b>{{item.price}}</b></span>起
                        <span class="like-addr">{{item.address}}</span>
                    </div>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default{
    data(){
        return{
            Likelist:[
                {
                    id:'01',
                    imgUrl:'http://img1.qunarzz.com/sight/p0/2011/e6/e6568888096dd6f3a3.water.jpg_200x200_3a5cf6a1.jpg',
                    title:'金海湖风景区',
                    address:'平谷区',
                    num:'1314',
                    price:'1452'
                },
                {
                    id:'02',
                    imgUrl:'http://img1.qunarzz.com/sight/p0/2011/f0/f050f346cfd6dc62a3.water.jpg_200x200_847c20bd.jpg',
                    title:'长隆野生动物世界',
                    address:'广州长隆',
                    num:'74556',
                    price:'285'
                },
                {
                    id:'03',
                    imgUrl:'http://img1.qunarzz.com/sight/p0/1603/20/208ed6bc971a41cf90.img.jpg_200x200_50c7ca89.jpg',
                    title:'宝墨园',
                    address:'番禺区',
                    num:'6416',
                    price:'28'
                },
                {
                    id:'04',
                    imgUrl:'http://img1.qunarzz.com/sight/p0/1603/1c/1c67791edbe2677b90.img.jpg_200x200_ff903759.jpg',
                    title:'珠江夜游',
                    address:'天河区',
                    num:'13416',
                    price:'24'
                },
                {
                    id:'05',
                    imgUrl:'http://img1.qunarzz.com/sight/p0/201309/06/a03726324b885c8bc8d65eac.jpg_200x200_109f2c42.jpg',
                    title:'广州塔',
                    address:'海珠区',
                    num:'646464',
                    price:'75'
                },
                {
                    id:'06',
                    imgUrl:'http://img1.qunarzz.com/sight/p0/1907/90/903428cd6de6a2c1a3.img.jpg_200x200_72b53792.jpg',
                    title:'广州融创雪世界',
                    address:'花都区',
                    num:'44512',
                    price:'190'
                },
                {
                    id:'07',
                    imgUrl:'http://img1.qunarzz.com/sight/p0/2011/e6/e6568888096dd6f3a3.water.jpg_200x200_3a5cf6a1.jpg',
                    title:'长隆欢乐世界',
                    address:'广州长隆',
                    num:'764641',
                    price:'230'
                }
            ]
        }
    }
}
</script>
<style scoped>
.like{
    margin-top: .2rem;
    font-size: .28rem;
    background: #fff;
    padding: 0 .2rem;
}
.like-top{
    padding: .2rem 0;
    font-size: .32rem;
}
.like-top img {
    width: 0.3rem;
    height: 0.3rem;
}
.like-item{
    padding: .2rem 0;
    position: relative;
    overflow: hidden;
}
.like-img{
    float: left;
}
.like-img img{
    width: 2rem;
    height: 2rem;
}
.like-text{
    overflow: hidden;
    padding-left: .22rem;
}
.like-title{
    font-size: .36rem;
    color: #212121;
    margin-top: .4rem;
}
.like-message{
    margin-top: .3rem;
    color: #616161;
    font-size: .24rem;
}
.like-map{
    margin-top: .3rem;
    color: #616161;
    font-size: .24rem;
    position: relative;
}
.like-mark{
    color: #ff8300;
    font-size: 0.32rem;
}
.like-addr{
    position: absolute;
    right: .24rem;
    bottom: 0;
}
</style>