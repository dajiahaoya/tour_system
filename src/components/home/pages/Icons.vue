<template>
    <div class="icons">
        <swiper ref="mySwiper" :options="swiperOptions" >
            <swiper-slide  
            v-for="(item,key) in page" 
            :key="key">
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
export default{
    data(){
        return{
            swiperOptions:{
                pagination: {
                    el: '.swiper-pagination'
                }
            },
            iconsList:[
                {
                    id:'01',
                    imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/158387fe5376294f3776d01358d6b73b.png',
                    title:'景点门票'
                },
                {
                    id:'02',
                    imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png',
                    title:'城市观光'
                },
                {
                    id:'03',
                    imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/b7a5e6b1774eda4fc9e32588f1d00c94.png',
                    title:'踏青赏花'
                },
                {
                    id:'04',
                    imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/aba25fb84648c130561afa5398d3552a.png',
                    title:'长隆动物园'
                },
                {
                    id:'05',
                    imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/5ffcd4a916f764f678263b27c1e2e00c.png',
                    title:'动植物园'
                },
                {
                    id:'06',
                    imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/c4c5c620f20535ff358788a508c20921.png',
                    title:'主题公园'
                },
                {
                    id:'07',
                    imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/69e8b07cb2d438c5530aebd4c8e3abd3.png',
                    title:'一日游'
                },
                {
                    id:'08',
                    imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/557ba25df01d7dbf1419b095a11d1319.png',
                    title:'泡温泉'
                },
                {
                    id:'09',
                    imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/a40ee278d67000f2a29d2e20f6a029b3.png',
                    title:'自然风光'
                },
                {
                    id:'10',
                    imgUrl:'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/59bc59a3c38261e9a3f2f991a9ce0d21.png',
                    title:'广州必游'
                }
            ]
        }
    },
    computed:{
        page (){
            let pages = [];
            this.iconsList.forEach((item,index)=>{
                let idx = Math.floor(index/8);
                if(!pages[idx])pages[idx] = [];
                pages[idx].push(item)
            })
            return pages;
        }
    }
}
</script>
<style scoped lang="stylus">
    @import '~css/common.styl';
    .icons{
        width: 100%;
        overflow: hidden;
        background: #fff;
    }
    .icons-item{
        width: 25%;
        height: 25%;
        float: left;
        margin-bottom: .2rem;
    }
    .icons-item img{
        width: 1.1rem;
        height: 1.1rem;
        display: block;
        margin: 0 auto;
        padding-top: .2rem;
    }
    .icons-item p{
        margin-top: .1rem;
        font-size: .28rem;
        text-align: center;
        color: #212121;
        textOverflow();
    }
    .swiper-pagination{
        bottom: 0;
    }
</style>