<template>
    <div class="header">
        <router-link to = "/">
            <div class="header-return" v-show="showHeader">
                <span class="border-return" ></span>
                <span class="iconfont return">&#xe624;</span>
            </div>
        </router-link>
        <div class="header-top" v-show="!showHeader" :style="styleOpacity">
            <div class="header-left">
                <span class="iconfont">
                    &#xe624;
                </span>
            </div>
            上海海昌水族館
        </div>
    </div>
</template>
<script>
export default{
    data(){
        return{
            showHeader:true,
            styleOpacity:{
                opacity:0
            }
        }
    },
    methods:{
       
    },
    mounted(){
        let That = this;
        window.addEventListener("scroll",function(){
            let top= document.documentElement.scrollTop;
            if(top > 45){
                let opacity = top/130;
                opacity = opacity>1 ? 1 : opacity
                That.styleOpacity = {opacity:1}
                That.showHeader = false;
            }else{
                That.showHeader = true;
            }
        })
    }
}
</script>
<style scoped lang="stylus">
    @import '~css/var.styl'
    .header-top{
        width: 100%;
        line-height: .88rem;
        background: #739eec;
        color: #fff;
        font-size: .36rem;
        overflow: hidden;
        text-align: center;
        position: fixed;
        top: 0;
    }
    .header-left{
        z-index: 99;
        position: absolute;
        width: .4rem;
        padding: 0 .2rem;
        text-align: center;
        font-weight: bold;
    }
.header-return{
    position: absolute;
    left: .1rem;
    top: .1rem;
    width: .72rem;
    height: .72rem;
}
.border-return{
    display: block;
    background: #000;
    width: .72rem;
    height: .72rem;
    opacity: .4;
    border-radius: .36rem;
}
.return{
    position: absolute;
    left: 0;
    top: 0;
    color: #fff;
    width: .72rem;
    height: .72rem;
    line-height: .72rem;
    text-align: left;
    text-indent: .24rem;
    font-size: .32rem;
    font-weight: bold;
    opacity: .7;
}
</style>