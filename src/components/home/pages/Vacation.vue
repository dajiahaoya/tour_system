<template>
    <div class="vacation">
        <div class="vacation-title">
            周末去哪
        </div>
            <ul>
                <li class="vacation-item" v-for="item in VacationList">
                    <div class="vacation-img">
                        <img :src="item.imgSrc" alt="">
                    </div>    
                    <div class="vacation-msg">
                        <p>{{item.title}}</p>
                        <p class="vacation-msg-dec">{{item.content}}</p>
                    </div>
                    </li>
                </li>
            </ul>
    </div>
</template>
<script>
export default{
    data () {
        return{
            VacationList:[
                {
                    id:'01',
                    imgSrc:'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
                    title:'清远周边逛',
                    content:'人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'
                },
                {
                    id:'02',
                    imgSrc:'http://img1.qunarzz.com/sight/source/1811/b8/5d599bbdcf8b57.jpg_r_640x214_2ee055e3.jpg',
                    title:'浮在海上的绿洲',
                    content:'南国滨海之城，避寒胜地，有暖暖的阳光，海风习习，吃着海鲜逛逛老街多惬意啊!'
                },
                {
                    id:'03',
                    imgSrc:'http://img1.qunarzz.com/sight/source/1602/9c/39c5ce9ff58609.jpg_r_640x214_efb90102.jpg',
                    title:'粤西温泉',
                    content:'自驾粤西，这里有最全最心仪的温泉池，环境优美，舒舒服服的泡个热汤，远离繁忙的工作'
                }
            ]
        }
    }
}
</script>
<style scoped lang="stylus">
@import '~css/common.styl';
.vacation-title{
    font-size: .32rem;
    padding: .24rem;
}
.vacation-item{
    margin-bottom: .1rem;
    background: #fff;
    font-size: .28rem;
}
.vacation-item img{
    width: 100%;
}
.vacation-img{
    width: 100%;
    height: 0;
    padding-bottom: 34.4375%;
}
.vacation-msg{
    padding: .2rem 0 .2rem .2rem;
}
.vacation-msg-dec{
    padding-right: 1.4rem;
    textOverflow();
}
.vacation-msg p{
    margin-top: .2rem;
}
.vacation-msg p+p{
    color: #616161;;
    font-size: .24rem;
}
</style>