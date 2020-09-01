<template>
    <div class="bottomNav">
        <div class="container">美团导航</div>
        <div class="hotSuggestions">
            <div class="hot" v-for="(item,index) in suggestionsList" :key="index">
                <div class="tittle">{{item.tittle}}</div>
                <div class="list">
                    <div class="cityName" v-for="(tem,i) in item.list" :key="i">
                        <a href>{{tem.text}}</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            suggestionsList: [
                {
                    tittle: "热门城市",
                    list: [
                        { text: "石家庄", src: "" },
                        {
                            text: "广州",
                            src: "",
                        },
                        {
                            text: "常州",
                            src: "",
                        },
                        {
                            text: "郑州",
                            src: "",
                        },
                        {
                            text: "北京",
                            src: "",
                        },
                        {
                            text: "深圳",
                            src: "",
                        },
                        {
                            text: "长春",
                            src: "",
                        },
                        {
                            text: "合肥",
                            src: "",
                        },
                        {
                            text: "贵阳",
                            src: "",
                        },
                        {
                            text: "福州",
                            src: "",
                        },
                        {
                            text: "西安",
                            src: "",
                        },
                        {
                            text: "东莞",
                            src: "",
                        },
                        {
                            text: "沈阳",
                            src: "",
                        },
                        {
                            text: "上海",
                            src: "",
                        },
                        {
                            text: "宁波",
                            src: "",
                        },
                        {
                            text: "哈尔滨",
                            src: "",
                        },
                        {
                            text: "苏州",
                            src: "",
                        },
                        {
                            text: "昆明",
                            src: "",
                        },
                        {
                            text: "太原",
                            src: "",
                        },
                        {
                            text: "厦门",
                            src: "",
                        },
                    ],
                },
                {
                    tittle: "热门分类",
                    list: [
                        { text: "酒店", src: "" },
                        { text: "美食", src: "" },
                        { text: "休闲娱乐", src: "" },
                        { text: "运动健身", src: "" },
                        { text: "生活服务", src: "" },
                        { text: "上门服务", src: "" },
                        { text: "购物", src: "" },
                        { text: "时尚购", src: "" },
                        { text: "本地购物", src: "" },
                        { text: "结婚", src: "" },
                        { text: "摄影写真", src: "" },
                        { text: "宴会", src: "" },
                        { text: "丽人", src: "" },
                        { text: "母婴母子", src: "" },
                        { text: "学习培训", src: "" },
                        { text: "家装", src: "" },
                        { text: "汽车服务", src: "" },
                        { text: "医疗", src: "" },
                        { text: "宠物", src: "" },
                    ],
                },
                {
                    tittle: "周边热门",
                    list: [
                        { text: "新津县酒店", src: "" },
                        { text: "崇州美食", src: "" },
                        { text: "崇州休闲娱乐", src: "" },
                        { text: "新津县运动", src: "" },
                        { text: "崇州生活服务", src: "" },
                        { text: "崇州上门服务", src: "" },
                        { text: "新津县购物", src: "" },
                        { text: "崇州时尚购", src: "" },
                        { text: "崇州本地购物", src: "" },
                        { text: "崇州结婚", src: "" },
                        { text: "彭州摄影写真", src: "" },
                        { text: "崇州宴会", src: "" },
                        { text: "彭州丽人", src: "" },
                        { text: "崇州母婴亲子", src: "" },
                        { text: "彭州学习培训", src: "" },
                        { text: "崇州家装", src: "" },
                        { text: "彭州汽车服务", src: "" },
                        { text: "崇州医疗", src: "" },
                        { text: "崇州宠物", src: "" },
                    ],
                },
            ],
        };
    },
    components: {},
};
</script>

<style scoped lang=less>
.bottomNav {
    border: 1px solid #e5e5e5;
    border-radius: 4px;
    background-color: white;
    box-sizing: border-box;
    color: #222;
    .container {
        height: 50px;
        font-size: 16px;
        font-weight: bold;
        box-sizing: border-box;
        padding-left: 20px;
        padding-top: 6px;
        line-height: 44px;
    }
    .hotSuggestions {
        .hot {
            height: 72px;
            .tittle {
                display: inline-block;
                color: #222;
                width: 100px;
                height: 40px;
                font-size: 14px;
                font-weight: bold;
                box-sizing: border-box;
                padding: 10px 0px;
                text-align: center;
                vertical-align: top;
            }
            .list {
                display: inline-block;
                width: 1088px;
                padding-top: 12px;
                vertical-align: top;
                border-bottom: 1px solid #e5e5e5;

                .cityName {
                    float: left;
                    width: 100px;
                    height: 17px;
                    font-size: 12px;
                    text-align: left;
                    margin-bottom: 13px;

                    a {
                        width: 80px;
                        color: #8d8d8d;
                        margin-right: 20px;
                        text-overflow: ellipsis;
                        white-space: nowrap;
                        overflow: hidden;
                    }
                }
            }
        }
    }
}
</style>