<template>
    <div class="top-bar">
        <div class="geo">
            <i class="el-icon-location" />
            成都
            <router-link class="changeCity" :to="{name: 'changeCity'}">切换城市</router-link>[
            <a href>新津县</a>
            <a href>崇州</a>
            <a href>彭州</a>
            ]
            <router-link class="login" :to="{name: 'login'}">立即登录</router-link>
            <router-link class="signup" :to="{name: 'signup'}">注册</router-link>
        </div>

        <div class="nav">
            <ul>
                <li>
                    <a href>我的美团</a>
                    <div class="list">
                        <div v-for="(item,index) in myMt" :key="index">{{ item }}</div>
                    </div>
                </li>

                <li>
                    <a class="not" href>手机APP</a>
                </li>

                <li>
                    <a href>商家中心</a>
                    <div class="list list-2">
                        <div v-for="(item,index) in shopCenter" :key="index">{{ item }}</div>
                    </div>
                </li>

                <li>
                    <a href>美团规则</a>
                    <div class="list">
                        <div v-for="(item,index) in mtRule" :key="index">{{ item }}</div>
                    </div>
                </li>

                <li>
                    <a href>网站导航</a>
                    <div class="list list-3">
                        <guide />
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
import guide from "./topBar/guide";

export default {
    name: "topbar",
    data() {
        return {
            myMt: ["我的订单", "我的收藏", "抵用券", "账户设置"],
            shopCenter: [
                "美团餐饮商户中心",
                "登录商家中心",
                "美团智能收银",
                "我想合作",
                "手机免费开店",
                "餐饮代理商招募",
                "商家申请开票",
                "免费合作美团排队",
            ],
            mtRule: ["规则中心", "规则目录", "规则评议院"],
        };
    },
    methods: {},
    components: {
        guide,
    },
};
</script>

<style scoped lang=less>
.top-bar {
    .geo {
        height: 40px;
        float: left;
        box-sizing: border-box;
        /* border: 1px solid black; */
        width: 595px;
        font-size: 12px;
        line-height: 40px;
        a {
            color: #999;
            &:hover {
                color: #fe8c00;
            }
        }
        .login {
            color: #fe8c00;
        }
    }
    .nav {
        height: 40px;
        line-height: 40px;
        /* border: 1px solid black; */
        float: right;
        text-align: right;
        font-size: 12px;
        box-sizing: border-box;
        width: 595px;
        ul {
            display: inline-block;
            vertical-align: top;
            li {
                display: inline-block;
                position: relative;
                box-sizing: border-box;
                width: 78px;
                height: 40px;
                text-align: left;
                /* border: 1px solid red; */
                a {
                    display: inline-block;
                    position: relative;
                    z-index: 2;
                    height: 41px;
                    width: 78px;
                    color: #999;
                    text-align: center;
                    box-sizing: border-box;
                    /* border: 1px solid black; */
                }
                .list {
                    width: 100% - 2px;
                    text-align: center;
                    position: absolute;
                    z-index: 99;
                    border: 1px solid #e5e5e5;
                    margin-top: -1px;
                    background-color: white;
                }
                .list-2 {
                    right: 0;
                    width: 120px;
                }
                .list-3 {
                    width: 1200px;
                    right: 0;
                    box-sizing: border-box;
                    border-top-left-radius: 4px;
                    padding: 30px 56px 36px 20px;
                }
            
                .list {
                    display: none;
                }
                &:hover {
                    & > a {
                        color: #fe8c00;
                        background-color: white;
                        border-left: 1px solid #e5e5e5;
                        border-right: 1px solid #e5e5e5;
                    }
                    & > .not {
                        background-color: initial;
                        border-left: none;
                        border-right: none;
                    }
                    & > .list {
                        display: block;
                    }
                }
            }
        }
    }
}
.top-bar::after {
    content: "";
    display: block;
    clear: both;
}
</style>