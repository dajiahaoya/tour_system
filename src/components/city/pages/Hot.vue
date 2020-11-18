<template>
    <div class="hot">
        <div class="hot-title">
            热门城市
        </div>
        <ul class="hot-list">
            <li class="hot-item">
                北京
            </li>
            <li class="hot-item">
                北京
            </li>
            <li class="hot-item">
                北京
            </li>
        </ul>
    </div>
</template>
<script>

</script>
<style scoped>
.hot{
    font-size: .28rem;
    background: #f5f5f5;
}
.hot-title{
    padding: .2rem;
}
.hot-list{
    position: relative;
    font-size: .28rem;
    display: flex;
    background: #fff;
    color: #212121;
}
.hot-list:before{
    content:" ";
    position: absolute;
    height: 100%;
    width: 33.3333%;
    left: 33.3333%;
    border-right: .02rem solid #ddd;
    border-left: .02rem solid #ddd;
}
.hot-item{
    flex: 4;
    text-align: center;
    height: .9rem;
    line-height: .9rem;
    border-bottom: .02rem solid #ddd;
}
</style>