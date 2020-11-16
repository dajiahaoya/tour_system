<template>
    <div class="icons">
        <swiper ref="mySwiper" :options="swiperOptions" >
            <swiper-slide  
            v-for="(item,key) in page" 
            :key="key">
                <div class="icons-item" v-for="page in item" :key = "page.id">
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
                    imgUrl:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1179273312,1128108760&fm=26&gp=0.jpg',
                    title:'景点门票'
                },
                {
                    id:'02',
                    imgUrl:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1179273312,1128108760&fm=26&gp=0.jpg',
                    title:'必游榜单'
                },
                {
                    id:'03',
                    imgUrl:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1179273312,1128108760&fm=26&gp=0.jpg',
                    title:'夏日玩水'
                },
                {
                    id:'04',
                    imgUrl:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1179273312,1128108760&fm=26&gp=0.jpg',
                    title:'主题乐园'
                },
                {
                    id:'05',
                    imgUrl:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1179273312,1128108760&fm=26&gp=0.jpg',
                    title:'动植物园'
                },
                {
                    id:'06',
                    imgUrl:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1179273312,1128108760&fm=26&gp=0.jpg',
                    title:'故宫'
                },
                {
                    id:'07',
                    imgUrl:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1179273312,1128108760&fm=26&gp=0.jpg',
                    title:'一日游'
                },
                {
                    id:'08',
                    imgUrl:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1179273312,1128108760&fm=26&gp=0.jpg',
                    title:'公园'
                },
                {
                    id:'09',
                    imgUrl:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1179273312,1128108760&fm=26&gp=0.jpg',
                    title:'游乐园'
                },
                {
                    id:'10',
                    imgUrl:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1179273312,1128108760&fm=26&gp=0.jpg',
                    title:'全部玩乐'
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
<style scoped>
    .icons{
        width: 100%;
        overflow: hidden;
    }
    .icons-item{
        width: 25%;
        padding-bottom: 25%;
        height: 0;
        float: left;
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
    }
</style>