<template>
    <div>
        <myContainer class="guess-bar" :nav="guessTag" />
        <div class="slider">
            <div class="slider-content">
                <a href class="guess-tab" v-for="(item,index) in guessList" :key="index">
                    <div class="card-content">
                        <div class="img-box">
                            <img class="product-img" :src="item.img" alt />
                        </div>
                        <div class="info">
                            <div class="product-tittle">{{item.tittle}}</div>
                            <div class="product-score">
                                <div class="stars">
                                    <ul class="stars-dark">
                                        <li></li>
                                        <li></li>
                                        <li></li>
                                        <li></li>
                                        <li></li>
                                    </ul>
                                    <ul class="stars-light">
                                        <li v-for="(item,index) in starScore" :key="index"></li>
                                    </ul>
                                </div>
                                <span class="judgement">{{item.judgement}}个评价</span>
                            </div>
                            <div class="address">{{item.address}}</div>
                            <p class="price">
                                <span>￥</span>
                                {{item.price}}
                                <span>起</span>
                            </p>
                        </div>
                    </div>
                </a>
            </div>
        </div>
    </div>
</template>

<script>
import myContainer from "./container";

export default {
    data() {
        return {
            guessTag: {
                tittle: "猜你喜欢",
                styleObject: {
                    background:
                        "linear-gradient(to right, rgb(88, 174, 221) 2%, rgb(66, 191, 205) 97%) rgb(88, 174, 221)",
                },
                list: [
                    {
                        text: "为您甄选最适合的",
                        tab: "on",
                    },
                ],
            },
            guessList: [
                {
                    img:
                        "https://p1.meituan.net/merchantpic/cee825eec41297e332b71dc0b94a78fa243588.jpg@214w_120h_1e_1c",
                    tittle: "Pinky.菲（凯德广场店）",
                    score: "",
                    judgement: "2327",
                    address: "凯德广场",
                    price: "1.0",
                },
                {
                    img:
                        "https://p1.meituan.net/bbia/2036fc6bd9838ae9acd432d01588e9ea118411.jpg@214w_120h_1e_1c",
                    tittle: "好利来（龙泉皇冠国际店）",
                    score: "4.5",
                    judgement: "399",
                    address: "北泉路",
                    price: "6.0",
                },
                {
                    img:
                        "https://p1.meituan.net/bbia/47391f97dd09c6d6385090346395fb9d302100.jpg@214w_120h_1e_1c",
                    tittle: "良木缘咖啡西餐（桐梓林店）",
                    score: "4",
                    judgement: "307",
                    address: "桐梓林",
                    price: "95.0",
                },
                {
                    img:
                        "https://p1.meituan.net/bbia/cb78e96a8932827ae49768f47f07c2e745385.jpg@214w_120h_1e_1c",
                    tittle: "蜀滋香鲜鱼坊（简阳店）",
                    score: "",
                    judgement: "182",
                    address: "老城区",
                    price: "89.9",
                },
                {
                    img:
                        "https://p1.meituan.net/bbia/16171594ef2177484a6f18e3905a66011938845.png@214w_120h_1e_1c",
                    tittle: "安德鲁森（交桂店）",
                    score: "4",
                    judgement: "85",
                    address: "西南交大",
                    price: "8.8",
                },
                {
                    img:
                        "https://p1.meituan.net/msmerchant/0bed864d5a881a96df4fa8011c13dc96136619.jpg@214w_120h_1e_1c",
                    tittle: "陈多多仙草屋（林湾夜市店）",
                    score: "3.5",
                    judgement: "10",
                    address: "",
                    price: "6.8",
                },
                {
                    img:
                        "https://p0.meituan.net/bbia/35fbe3f5bd0743d79d10e843c40615b6737238.png@214w_120h_1e_1c",
                    tittle: "巴黎甜甜生日蛋糕连锁（大丰店）",
                    score: "5",
                    judgement: "279",
                    address: "大丰",
                    price: "99.8",
                },
                {
                    img:
                        "https://p1.meituan.net/msmerchant/7fc1b20768eff80b857c83632c04fc1b65091.jpg@214w_120h_1e_1c",
                    tittle: "行大田牛排海鲜自助（海滨城店）",
                    score: "4",
                    judgement: "7839",
                    address: "蛟龙港/海滨城",
                    price: "49.9",
                },
                {
                    img:
                        "https://p1.meituan.net/mogu/b04a76c4d28c33a3f3458e5008938da2596478.jpg@214w_120h_1e_1c",
                    tittle: "盘古烤肉店（春熙路店）",
                    score: "5",
                    judgement: "3781",
                    address: "春熙路",
                    price: "16.8",
                },
                {
                    img:
                        "https://p0.meituan.net/msmerchant/48493995a17854bb5831cfef6baf18fb583829.jpg@214w_120h_1e_1c",
                    tittle: "小猪猪烤肉（群光广场店）",
                    score: "4.5",
                    judgement: "6516",
                    address: "春熙路",
                    price: "85",
                },
                {
                    img:
                        "https://p0.meituan.net/mogu/7306787fd12fa378a5b0d7ea2d254988231662.png@214w_120h_1e_1c",
                    tittle: "鱼儿纸包鱼（蜀都万达直营店）",
                    score: "4",
                    judgement: "2055",
                    address: "蜀都万达",
                    price: "68.8",
                },
                {
                    img:
                        "https://p1.meituan.net/msmerchant/b946b85509b74bed4437764993148439822991.jpg@214w_120h_1e_1c",
                    tittle: "芭菲盛宴·环球美食（奥克斯广场店）",
                    score: "4",
                    judgement: "33098",
                    address: "环球中心",
                    price: "129.0",
                },
                {
                    img:
                        "https://p1.meituan.net/msmerchant/292d1b545c50f1fdcd7555592e82b9631182485.jpg@214w_120h_1e_1c",
                    tittle: "城门口老火锅（长寿路店）",
                    score: "4",
                    judgement: "8930",
                    address: "科华中路王府井",
                    price: "50.0",
                },
                {
                    img:
                        "https://p0.meituan.net/merchantpic/707129709645d80708465003c379be39271738.jpg@214w_120h_1e_1c",
                    tittle: "格式化照相馆（春熙路店）",
                    score: "5",
                    judgement: "4010",
                    address: "春熙路/太古里",
                    price: "39.9",
                },
                {
                    img:
                        "https://p1.meituan.net/bbia/a369faa7ca98b0982c01eece34323175240585.jpg@214w_120h_1e_1c",
                    tittle: "一洋刺身·日式串烧酒场（二十四城店）",
                    score: "5",
                    judgement: "1134",
                    address: "塔子山公园",
                    price: "92.0",
                },
            ],
        };
    },
    methods: {},
    components: {
        myContainer,
    },
};
</script>

<style scoped lang=less>
.slider {
    background-color: white;
    padding: 10px;
    border: 1px solid #e5e5e5;
    border-top: 0;
    border-bottom-left-radius: 4px;
    border-bottom-right-radius: 4px;
    width: 100%;
    box-sizing: border-box;

    .slider-content {
        &::after {
            content: "";
            display: block;
            clear: both;
        }
        /* border: 1px solid black; */
        & > a {
            width: 20%;
            /* border:1px solid red; */
            display: inline-block;
            /* vertical-align: middle; */
            .card-content {
                padding: 10px;
                &:hover {
                    background-color: #f4f4f4;
                    border-radius: 4px;
                    transition: background-color 500ms;
                }
                .img-box {
                    widows: 100%;
                    border-radius: 4px;
                    overflow: hidden;
                    background-size: cover;
                    img {
                        width: 100%;
                    }
                }
                .info {
                    .product-tittle {
                        font-size: 16px;
                        white-space: nowrap;
                        overflow: hidden;
                        text-overflow: ellipsis;
                        color: #222222;
                        font-weight: bold;
                        height: 22px;
                        line-height: 22px;
                    }
                    .product-score {
                        height: 24px;
                        .judgement {
                            font-size: 12px;
                            color: #999;
                            height: 24px;
                            line-height: 24px;
                            margin-left: 10px;
                        }
                    }

                    .address {
                        font-size: 12px;
                        color: #999999;
                        height: 18px;
                        line-height: 18px;
                        overflow: hidden;
                        text-overflow: ellipsis;
                        white-space: nowrap;
                    }
                }
            }
        }
    }
}
</style>