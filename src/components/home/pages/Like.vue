<template>
    <div class="like">
        <div class="like-top">
            <img src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="">
            猜你喜欢
        </div>
        <ul>
            <li class="like-item border-bottom" v-for="item in likeList">
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
    props:['likeList'],
    data(){
        return{
            
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