<template>
    <div class="vacation">
        <div class="vacation-title">
            周末去哪
        </div>
            <ul>
                <li class="vacation-item" v-for="item in vacationList">
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
    props:['vacationList'],
    data () {
        return{
            
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
    overflow: hidden;
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