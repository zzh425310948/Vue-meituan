<template>
    <div class="banner">
        <div class="left-banner">
            <div class="tittle-wraper">全部分类</div>
            <ul class="content-wraper">
                <li v-for="(item,index) in iconList" :key="index" class="nav-li">
                    <i :class="item.class" class="iconfont listicon" :style="item.styleObject"></i>
                    <span class="list-text">
                        <span v-for="(item2,i) in item.tittle" :key="i">
                            <a href>{{item2.text}}</a>
                            <span v-if="i < item.tittle.length - 1">/</span>
                        </span>
                    </span>
                    <i class="iconfont icon-arrow-right"></i>
                </li>
            </ul>
        </div>
        <div class="right-banner">
            <div class="list1">
                <div class="list1-1">
                    <el-carousel :interval="5000" height="240px">
                        <el-carousel-item v-for="(item,index) in changeList" :key="index">
                            <a href>
                                <div class="slider-img-div" :style="{backgroundImage: item.inSrc}"></div>
                            </a>
                        </el-carousel-item>
                    </el-carousel>
                </div>
                <div class="list1-2">
                    <a href>
                        <img
                            src="http://p0.meituan.net/codeman/e473bb428f070321269b23370ff02ba956209.jpg"
                            alt
                        />
                    </a>
                </div>

                <div class="list1-3">
                    <div class="head-img-p">
                        <img
                            src="https://s0.meituan.net/bs/fe-web-meituan/e350c4a/img/avatar.jpg"
                            alt
                        />
                    </div>
                    <div class="user-name">Hi! 你好</div>
                    <a href class="btn-login">注册</a>
                    <a href class="btn-login">立即登录</a>
                </div>
            </div>
            <div class="list2">
                <div class="list2-1">
                    <a href>
                        <img
                            src="http://p1.meituan.net/codeman/8cce56c467a17e04f3094d1e455462a0132772.png"
                            alt
                        />
                    </a>
                </div>
                <div class="list2-2">
                    <a href>
                        <img
                            src="http://p1.meituan.net/codeman/16442c19da1f1c4544f794e29d99c92051716.jpg"
                            alt
                        />
                    </a>
                </div>
                <div class="list2-3">
                    <a href>
                        <img
                            src="http://p1.meituan.net/codeman/5b21cddb4bb1cbc3a9c3bce0f726c75940469.jpg"
                            alt
                        />
                    </a>
                </div>
                <div class="list2-4">
                    <img
                        class="qrcode"
                        src="https://s1.meituan.net/bs/fe-web-meituan/60ac9a0/img/download-qr.png"
                        alt
                    />
                    <p class="app-name">美团APP手机版</p>
                    <p class="sl">
                        <span class="red">1元起</span>
                        <span class="gary">吃喝玩乐</span>
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            changeList: [
                {
                    inSrc:
                        "url(http://p0.meituan.net/codeman/daa73310c9e57454dc97f0146640fd9f69772.jpg)",
                },
                {
                    inSrc:
                        "url(http://p1.meituan.net/codeman/826a5ed09dab49af658c34624d75491861404.jpg)",
                },
                {
                    inSrc:
                        "url(http://p0.meituan.net/codeman/a97baf515235f4c5a2b1323a741e577185048.jpg)",
                },
                {
                    inSrc:
                        "url(http://p0.meituan.net/codeman/33ff80dc00f832d697f3e20fc030799560495.jpg)",
                },
                {
                    inSrc:
                        "url(https://p1.meituan.net/travelcube/01d2ab1efac6e2b7adcfcdf57b8cb5481085686.png)",
                },
            ],
            iconList: [],
        };
    },
    created() {
        axios.get('https://www.fastmock.site/mock/a7fdfe59948bf7e5e2764cd0b5e7ce30/meituan/api/getTypeList').then((response) => {
            this.iconList = response.data.iconList
        });
    },
};
</script>

<style scoped lang=less>
.banner {
    position: relative;
    &::after {
        content: "";
        display: block;
        clear: both;
    }
    .left-banner {
        position: absolute;
        bottom: 0px;
        float: left;
        width: 230px;
        height: 475px;
        border: 1px solid #e5e5e5;
        background-color: white;
        box-sizing: border-box;

        .tittle-wraper {
            margin-top: 12px;
            margin-left: 15px;
            padding-bottom: 22px;
            font-size: 16px;
            color: black;
        }
        .content-wraper {
            height: 417px;
            .nav-li {
                height: 100%/16;
                padding: 0px 13px;
                position: relative;
                .listicon {
                    font-size: 15px;
                }
                .list-text {
                    font-size: 13px;
                    margin-left: 10px;
                }
                .icon-huochepiao {
                    font-size: 12px;
                    margin-left: -4px;
                }
                .icon-arrow-right {
                    position: absolute;
                    font-size: 12px;
                    display: inline-block;
                    right: 5px;
                    top: 6px;
                }
            }
        }
    }
    .right-banner {
        float: right;
        width: 950px;
        height: 417px;
        box-sizing: border-box;
        .list1 {
            height: 240px;
            margin-bottom: 10px;
            .list1-1 {
                float: left;
                margin-right: 10px;
                width: 550px;
                height: 100%;
                .el-carousel__item {
                    .slider-img-div {
                        width: 100%;
                        height: 100%;
                        background-repeat: no-repeat;
                        background-position: 50%;
                        background-size: cover;
                    }
                }
            }
            .list1-2 {
                float: left;
                width: 150px;
                height: 240px;
                margin-right: 10px;
                img {
                    height: 100%;
                }
            }
            .list1-3 {
                float: left;
                width: 230px;
                height: 240px;
                background-color: white;
                border: 1px solid #e5e5e5;
                box-sizing: border-box;
                text-align: center;
                .head-img-p {
                    margin-top: 30px;
                    text-align: center;
                    img {
                        width: 47px;
                        height: 47px;
                        border-radius: 50%;
                        border: 4px solid #e5e5e5;
                    }
                }
                .user-name {
                    font-weight: bold;
                    font-size: 16px;
                    color: #222;
                    white-space: nowrap;
                    width: 6em;
                    overflow: hidden;
                    text-overflow: ellipsis;
                    margin: 0 auto;
                }
                .btn-login {
                    display: block;
                    margin: 10px auto 15px auto;
                    width: 118px;
                    height: 38px;
                    line-height: 38px;
                    font-size: 14px;
                    border: 1px solid #e5e5e5;
                    background: #fff;
                    border-radius: 30px;
                    transition: background-color 0.5s;
                    &:hover {
                        background-color: #f6f6f6;
                    }
                }
            }
        }
        .list2 {
            height: 167px;
            box-sizing: border-box;
            .list2-1 {
                float: left;
                width: 270px;
                height: 167px;
                margin-right: 10px;
                img {
                    width: 100%;
                }
            }
            .list2-2 {
                float: left;
                width: 270px;
                margin-right: 10px;
                img {
                    height: 100%;
                }
            }
            .list2-3 {
                float: left;
                width: 150px;
                margin-right: 10px;
                img {
                    width: 100%;
                }
            }
            .list2-4 {
                float: left;
                width: 230px;
                height: 167px;
                background-color: white;
                border: 1px solid #e5e5e5;
                box-sizing: border-box;
                text-align: center;
                .qrcode {
                    display: block;
                    width: 95px;
                    height: 95px;
                    margin: 10px auto 3px;
                }
                .app-name {
                    font-size: 16px;
                    color: #222222;
                    font-weight: 500;
                }
                .sl {
                    font-size: 12px;
                    font-weight: 500;
                    margin-top: 2px;
                    .red {
                        color: #ec5330;
                        margin-right: 5px;
                    }
                    .gary {
                        color: #3f3f3f;
                    }
                }
            }
        }
    }
}
</style>