<template>
    <div class="wrapper">
        <div class="top">
            <div class="left">
                <i class="iconfont icon-fanhui" @click="$router.push({name: 'list'})"></i>
                {{info.name }}
            </div>

            <i class="iconfont icon-gengduo"></i>
        </div>

        <div class="main">
            <div class="time">
                {{info.time}}
            </div>

            <div class="pay">
                <img :src="info.img" alt="">
                <div class="money">
                    <span>
                        {{info.money}}
                    </span>
                </div>
            </div>
        </div>

        <div class="footer">
            <i class="iconfont icon-yuyin"></i>
            <div></div>
            <i class="iconfont icon-biaoqing"></i>

            <i class="iconfont icon-jiahao"></i>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            info: {}
        }
    },
    created() {
        this.info = {  
            name: '简简单单',
            money: 88,
            ...this.$route.query,
        }
    }
}
</script>

<style lang="scss" scoped>
.top {
    height: 50px;
    background:  rgb(48,48,48);;
    width: 100%;
    color: white;
    line-height: 50px;
    padding: 0 15px;
    display: flex;
    box-sizing: border-box;
    justify-content: space-between;
    align-items: center;
    position: relative;
    i {
        font-size: 18px;
    }
    >.left {
        display: flex;
        align-items: center;
        font-size: 16px;
        >i {
            margin-right: 10px;
        }
    }
    .mid {
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%,-50%);
    }
}
.main {
    text-align: center;

    .time {
        background: rgba(0, 0, 0, 0.1);
        height: 20px;
        line-height: 20px;
        font-size: 12px;
        padding: 0 8px;
        border-radius: 5px;
        max-width: 50%;
        color: white;
        display: inline-block;
        margin: 8px auto;
    }
    .pay {
        display: flex;
        padding-left: 15px;
        > img {
            width: 49px;
            height: 49px;
            margin-right: 10px;
        }
        > .money {
            background-image: url('../assets/android1.png');
            width: 60%;
            background-size: contain;
            background-repeat: no-repeat;
            height: 90px;
            position: relative;
            > span {
                font-size: 12px;
                color: white;
                position: absolute;
                top: 30px;
                left: 62px;
                @media screen and (min-width: 380px) {
                    & {
                        top: 34px;
                        left: 68px;
                    }
                }
            }
        }
    }
}
.footer {
    height: 50px;
    position: fixed;
    background: #f6f6f8;
    left: 0;
    bottom: 0;
    width: 100%;
    border-top: 1px solid #ddd;
    padding: 0 15px;
    box-sizing: border-box;
    color: #999;
    display: flex;
    justify-content: space-between;
    align-items: center;
    > i {
        font-size: 30px;
    }
    > div {
        width: 67%;
        border-bottom: 1px solid #ddd;
        height: 38px;
        // border-radius: 3px;
        // background: white;
        align-self: flex-start;
    }
}
</style>

