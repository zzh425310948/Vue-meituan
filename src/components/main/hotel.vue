<template>
    <div>
        <myContainer :nav="hotelTag" />
        <div class="hotel-view">
            <div class="productsList">
                <div class="hotel-tab" v-for="(item,index) in hotels" :key="index">
                    <a href>
                        <div class="product-img">
                            <img :src="item.img" alt />
                        </div>
                        <div class="produck-info">
                            <p class="product-tittle">{{ item.tittle }}</p>
                            <p class="sub-tittle">
                                <span>整租{{ item.roomNum }}居室·</span>
                                <span>可住{{ item.peopelNum }}人 |</span>
                                <span>{{ item.nearAdress }}</span>
                            </p>
                            <p class="price">
                                <span class="price-icon">￥</span>{{item.price}}
                            </p>
                        </div>
                    </a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import myContainer from "./container";
export default {
    data() {
        return {
            hotelTag: {
                tittle: "民宿推荐",
                styleObject: {
                    background: "linear-gradient(to right,rgb(243, 182, 74) 2%,rgb(242, 197, 69) 97%)rgb(243, 182, 74)"
                },
                list: [
                    { text: "重庆", tab: "chongqin" },
                    { text: "绵阳", tab: "mianyang" },
                    { text: "乐山", tab: "leshan" },
                    { text: "凉山", tab: "liangshan" },
                    { text: "彝族自治州", tab: "yizu" },
                    { text: "遵义", tab: "zunyi" },
                    { text: "自贡", tab: "zigong" },
                    { text: "雅安", tab: "yaan" },
                    { text: "宜宾", tab: "yibin" },
                    { text: "内江", tab: "neijiang" },
                    { text: "泸州", tab: "luzhou" },
                ],
            },
            hotels: [
                {
                    img:
                        "https://img.meituan.net/phoenix/938b101cc5db9d94cf309250fd04fd96293073.jpg@740w_416h_1e_1c",
                    tittle:
                        "每日消毒/紧邻解放碑洪崖洞步行可达长嘉汇 /弹子石老街 /临地铁 /轻奢大床房_清风小筑",
                    roomNum: "1",
                    peopelNum: "2",
                    nearAdress: "洋人街、弹子石",
                    price: 129,
                },
                {
                    img:"https://img.meituan.net/phoenix/f37a00d67ce7fdc1db02d8a9046d81523463112.jpg@740w_416h_1e_1c",
                    tittle:"【已消毒】观音桥步行街/九街北仓文化/近解放碑洪崖洞宜家风温柔小居",
                    roomNum: "1",
                    peopelNum: "2",
                    nearAdress: "观音桥/九街",
                    price: 168,
                },{
                    img:"http://p1.meituan.net/iphoenix/59e1da734fcf851280d1a9877e7252597173349.jpg@740w_416h_1e_1c",
                    tittle:"【一番星】落地窗豪华江景一室一厅｜轻奢浴缸小米智能电视｜近解放碑洪崖洞南滨路各大景点｜可做饭｜全屋消毒放心入住",
                    roomNum: "1",
                    peopelNum: "2",
                    nearAdress: "南滨路",
                    price: 275,
                },{
                    img:"https://img.meituan.net/phoenix/33ee82c0a1b66a31d8fbc1bf10e96fb0524715.jpg@740w_416h_1e_1c",
                    tittle:"微客公馆的W十公寓",
                    roomNum: "1",
                    peopelNum: "2",
                    nearAdress: "重庆大学城",
                    price: 108,
                },{
                    img:"http://p0.meituan.net/iphoenix/5aa93591100bf820be6d857a720df5984329789.jpg@740w_416h_1e_1c",
                    tittle:"【已消毒】源著天街旁公寓、靠近购物广场和轻轨站、房间大、有洗衣机、适合长租的哟",
                    roomNum: "1",
                    peopelNum: "2",
                    nearAdress: "冉家坝/龙溪",
                    price: 118,
                },{
                    img:"https://img.meituan.net/iphoenix/e51b044aef7a6d6f144cecf76bbfe78e242311.jpg@740w_416h_1e_1c",
                    tittle:"【仓央嘉措的隐逸庄园】英式庄园可做饭一居/全线江景/长江大桥旁/近解放碑洪崖洞江景/近南山一棵树观景台",
                    roomNum: "1",
                    peopelNum: "2",
                    nearAdress: "南滨路",
                    price: 248,
                },
            ],
        };
    },
    components: {
        myContainer,
    },
};
</script>

<style scoped lang=less>

.hotel-view {
    height: 691px;
    box-sizing: border-box;
    padding-left: 20px;
    padding-top: 20px;
    border: 1px solid #e5e5e5;
    border-top: 0px;
    border-bottom-left-radius: 4px;
    border-bottom-right-radius: 4px;
    background-color: white;
    .productsList {
        width: 1168px;
        height: 670px;
        .hotel-tab {
            width: 370px;
            height: 335px;
            margin-right: 18px;
            float: left;
            /* border: 1px solid red; */
            .product-img {
                position: relative;
                width: 370px;
                height: 222px;
                img {
                    position: absolute;
                    width: 370px;
                    height: 208px;
                    border-radius: 4px;
                    margin-bottom: 11px;
                }
            }
            .produck-info {
                .product-tittle {
                    width: 297px;
                    font-size: 16px;
                    color: #222222;
                    overflow: hidden;
                    text-overflow: ellipsis;
                    white-space: nowrap;
                    margin: 7px 0;
                }
                .sub-tittle {
                    font-size: 12px;
                    color: #999999;
                    text-align: left;
                }
                .price {
                    font-size: 22px;
                    color: #ff6600;
                    padding: 4px 0;
                    .price-icon {
                        font-size: 14px;
                    }
                }
            }
        }
    }
}
</style>