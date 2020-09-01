<template>
    <div class="search" id="search">
        <div class="img">
            <a href>
                <img src="../assets/img/logo.png" alt />
            </a>
        </div>
        <div class="input">
            <input class="put" type="text" />
            <button class="button">
                <span class="iconfont icon-search"></span>
            </button>
        </div>
        <div class="nav">
            <a v-for="(item,index) in navList" :key="index" href>{{ item }}</a>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            navList: [
                "美团外卖",
                "猫眼电影",
                "美团酒店",
                "民宿／公寓",
                "商家入驻",
                "美团公益",
            ],
        };
    },
};
</script>

<style scoped lang=less>
#search {
    width: 1190px;
    position: relative;
    box-sizing: border-box;
    text-align: center;

    /* border: 1px solid black; */
    .img {
        float: left;
        position: absolute;
        padding-top: 28px;
        padding-right: 60px;
        padding-bottom: 40px;
        a {
            /* border: 1px solid black; */
            img {
                width: 126px;
                height: 46px;
            }
        }
    }
    .input {
        display: inline-block;
        margin: 0 auto;
        margin-top: 28px;
        width: 550px;
        height: 40px;
        font-size: 14px;
        box-sizing: border-box;
        .put {
            display: inline-block;
            width: 85.5%;
            height: 40px;
            padding: 15px;
            border: 1px solid #e5e5e5;
            box-sizing: border-box;
            border-radius: 4px 0px 0px 4px;
            border-right: none;
            vertical-align: top;
        }
        .button {
            width: 14.5%;
            height: 40px;
            box-sizing: border-box;
            background: #ffc300;
            border-radius: 0px 4px 4px 0px;
            border: none;
            cursor: text;
            .icon-search {
                border: none;
                font-size: 18px;
                font-weight: bold;
            }
        }
    }
    .nav {
        margin: 0 auto;
        margin-top: 52px;
        width: fit-content;
        /* border: 1px solid black; */
        a {
            margin: auto 20px;
            font-size: 16px;
            color: black;
        }
    }
}
</style>