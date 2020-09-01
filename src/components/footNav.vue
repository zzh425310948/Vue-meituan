<template>
    <div>
        <div class="footer">
            <div class="row-list" v-for="(item,index) in allList" :key="index">
                <dl class="singleList" v-for="(item2,index2) in item.singleList" :key="index2">
                    <dt class="tittle">{{item2.tittle}}</dt>
                    <dd v-for="(item3,i) in item2.list" :key="i">
                        <a href>{{item3.text}}</a>
                    </dd>
                </dl>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            allList: [
                {
                    singleList: [
                        {
                            tittle: "用户帮助",
                            list: [
                                {
                                    text: "申请退款",
                                    src: "",
                                },
                                {
                                    text: "查看美团券密码",
                                    src: "",
                                },
                                {
                                    text: "常见问题",
                                    src: "",
                                },
                                {
                                    text: "用户协议",
                                    src: "",
                                },
                                {
                                    text: "隐私政策",
                                    src: "",
                                },
                                {
                                    text: "反诈骗公告",
                                    src: "",
                                },
                                {
                                    text: "消费者权益保障",
                                    src: "",
                                },
                            ],
                        },
                        {
                            tittle: "美团服务",
                            list: [
                                {
                                    text: "美团外卖",
                                    src: "",
                                },
                                {
                                    text: "美团酒店",
                                    src: "",
                                },
                                {
                                    text: "猫眼电影",
                                    src: "",
                                },
                                {
                                    text: "美团配送",
                                    src: "",
                                },
                                {
                                    text: "美团云",
                                    src: "",
                                },
                                {
                                    text: "大众点评",
                                    src: "",
                                },
                                {
                                    text: "美团民宿",
                                    src: "",
                                },
                                {
                                    text: "无人配送",
                                    src: "",
                                },
                            ],
                        },
                    ],
                },
                {
                    singleList: [
                        {
                            tittle: "商家合作",
                            list: [
                                {
                                    text: "美团餐饮商户中心",

                                    src: "",
                                },
                                {
                                    text: "美食商家入驻(非外卖)",
                                    src: "",
                                },
                                {
                                    text: "美团外卖开店申请",
                                    src: "",
                                },
                                {
                                    text: "美团收银官网",
                                    src: "",
                                },
                                {
                                    text: "外卖配送加盟申请",
                                    src: "",
                                },
                                {
                                    text: "美团点评餐饮学院",
                                    src: "",
                                },
                                {
                                    text: "酒店商家入驻",
                                    src: "",
                                },
                                {
                                    text: "境内度假商家入驻",
                                    src: "",
                                },
                                {
                                    text: "综合商家入驻",
                                    src: "",
                                },
                                {
                                    text: "美团民宿房东商家入驻",
                                    src: "",
                                },
                                {
                                    text: "商家开票申请",
                                    src: "",
                                },
                                {
                                    text: "美团点评智能收银机",
                                    src: "",
                                },
                                {
                                    text: "美团点评餐饮开放平台",
                                    src: "",
                                },
                                {
                                    text: "美团点评收单",
                                    src: "",
                                },
                                {
                                    text: "免费使用美团排队",
                                    src: "",
                                },
                                {
                                    text: "快驴进货商家合作",
                                    src: "",
                                },
                                {
                                    text: "美团闪购商家入驻",
                                    src: "",
                                },
                            ],
                        },
                    ],
                },
                {
                    singleList: [
                        {
                            tittle: "代理商加盟",
                            list: [
                                {
                                    text: "美团外卖代理商招募",
                                    src: "",
                                },
                                {
                                    text: "到店餐饮代理商招募",
                                    src: "",
                                },
                                {
                                    text: "非餐饮代理商招募",
                                    src: "",
                                },
                                {
                                    text: "美团联盟",
                                    src: "",
                                },
                                {
                                    text: "美团收银招募线上分销商",
                                    src: "",
                                },
                                {
                                    text: "美团点评5S服务商招募",
                                    src: "",
                                },
                                {
                                    text: "",
                                    src: "",
                                },
                                {
                                    text: "美团收单渠道代理商招募",
                                    src: "",
                                },
                            ],
                        },
                        {
                            tittle: "美团规则",
                            list: [
                                {
                                    text: "规则中心",
                                    src: "",
                                },
                                {
                                    text: "规则目录",
                                    src: "",
                                },
                                {
                                    text: "规则评议院",
                                    src: "",
                                },
                            ],
                        },
                    ],
                },
                {
                    singleList: [
                        {
                            tittle: "关注美团",
                            list: [
                                {
                                    text: "美团新浪微博",
                                    src: "",
                                },
                            ],
                        },
                        {
                            tittle: "公司信息",
                            list: [
                                {
                                    text: "关于我们",
                                    src: "",
                                },
                                {
                                    text: "投资者关系",
                                    src: "",
                                },
                                {
                                    text: "加入我们",
                                    src: "",
                                },
                                {
                                    text: "商户诚信公约及管理办法",
                                    src: "",
                                },
                                {
                                    text: "保险经纪资质",
                                    src: "",
                                },
                            ],
                        },
                        {
                            tittle: "廉正举报",
                            list: [
                                {
                                    text: "廉正举报平台",
                                    src: "",
                                },
                            ],
                        },
                        {
                            tittle: "知识产权",
                            list: [
                                {
                                    text: "知识产权维护平台",
                                    src: "",
                                },
                            ],
                        },
                    ],
                },
                {
                    singleList: [
                        {
                            tittle: "消费者服务热线",
                            list: [
                                {
                                    text: "外卖消费者：10109777",
                                    src: "",
                                },
                                {
                                    text: "猫眼消费者：10105335",
                                    src: "",
                                },
                                {
                                    text: "其他消费者：10107888",
                                    src: "",
                                },
                            ],
                        },
                        {
                            tittle: "商家服务热线",
                            list: [
                                {
                                    text: "外卖&餐饮商家：10105557",
                                    src: "",
                                },
                                {
                                    text:
                                        "休闲娱乐、丽人、ktv、教育、结婚、亲子、家装等商家：10100107",
                                    src: "",
                                },
                            ],
                        },
                        {
                            tittle: "投诉举报专区",
                            list: [
                                {
                                    text: "违法和不良信息举报电话：4006018900",
                                    src: "",
                                },
                                {
                                    text: "举报邮箱：tousujubao@meituan.com",
                                    src: "",
                                },
                                {
                                    text: "网上有害信息举报",
                                    src: "",
                                },
                            ],
                        },
                    ],
                },
            ],
        };
    },
};
</script>

<style scoped lang=less>
.footer {
    margin-top: 40px;
    border-top: 1px solid #e5e5e5;
    padding: 40px 45px;
    .row-list {
        display: inline-block;
        width: 20%;
        vertical-align: top;
        .singleList {
            padding-bottom: 20px;
            .tittle {
                color: #333;
                font-size: 14px;
                font-weight: 500;
                line-height: 2;
            }
            > dd {
                font-size: 12px;
                color: rgb(133, 133, 133);
                line-height: 2;
            }
        }
    }
}
</style>