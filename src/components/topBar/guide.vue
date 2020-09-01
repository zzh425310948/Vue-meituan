<template>
    <div class="guide">
        <div class="travel">
            <header>酒店旅游</header>
            <div>
                <router-link v-for="(item,index) in travel" :key="index" to>{{ item }}</router-link>
            </div>
        </div>
        <div class="food">
            <header>吃美食</header>
            <div>
                <router-link v-for="(item,index) in food" :key="index" to>{{ item }}</router-link>
            </div>
        </div>
        <div class="movies">
            <header>看电影</header>
            <div>
                <router-link v-for="(item,index) in movies" :key="index" to>{{ item }}</router-link>
            </div>
        </div>
        <div class="phone">
            <header>手机应用</header>
            <a href>
                <img
                    class="appicon"
                    src="//s0.meituan.net/bs/fe-web-meituan/2d53095/img/appicons/meituan.png"
                    title="美团app"
                    alt="美团app"
                />
            </a>
            <a href>
                <img
                    class="appicon"
                    src="//s1.meituan.net/bs/fe-web-meituan/404d350/img/appicons/waimai.png"
                    title="外卖app"
                    alt="外卖app"
                />
            </a>
            <a href>
                <img
                    class="appicon"
                    src="https://p0.meituan.net/travelcube/162c3308d9622f6d9cfaa49e60be4dca8573.png"
                    title="民宿app"
                    alt="民宿app"
                />
            </a>
            <a href>
                <img
                    class="appicon"
                    src="//s1.meituan.net/bs/fe-web-meituan/404d350/img/appicons/dianping.png"
                    title="点评app"
                    alt="点评app"
                />
            </a>
            <a href>
                <img
                    class="appicon"
                    src="//s1.meituan.net/bs/fe-web-meituan/404d350/img/appicons/maoyan.png"
                    title="猫眼app"
                    alt="猫眼app"
                />
            </a>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            travel: [
                "国际机票",
                "火车票",
                "民宿",
                "经济型酒店",
                "主题酒店",
                "商务酒店",
                "公寓",
                "豪华酒店",
                "客栈",
                "青年旅社",
                "度假酒店",
                "别墅",
                "农家院",
            ],
            food: ["烤鱼", "特色小吃", "烧烤", "自助餐", "火锅", "代金券"],
            movies: [
                "热映电影",
                "热门影院",
                "热映电影口碑榜",
                "最受期待电影",
                "国内票房榜",
                "北美票房榜",
                "电影排行榜",
            ],
        };
    },
};
</script>

<style scoped lang=less>
.guide {
    margin: 0 auto;
    /* border: 1px solid black; */
    > div {
        margin: 0 30px;
        /* border: 1px solid red; */
        float: left;
        header {
            font-size: 14px;
            height: 20px;
            line-height: 20px;
            /* border: 1px solid black; */
            margin-bottom: 26px;
        }
        div {
            a {
                float: left;
                height: 16px;
                line-height: 16px;
                text-align: center;
                margin: 5px 0;
                /* border: 1px solid black; */
                box-sizing: border-box;
            }
        }
    }

    .travel {
        width: 234px;
        div a {
            width: 33%;
            /* border: 1px solid black; */
        }
    }
    .food {
        width: 156px;
        div a {
            width: 50%;
        }
    }
    .movies {
        width: 90px;
        div a {
            width: 100%;
        }
    }
    .phone {
        float: right;
        img {
            width: 60px;
            height: 60px;
        }
    }

}
</style>