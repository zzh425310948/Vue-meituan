<template>
    <div class="container" :style="nav.styleObject">
        <dl @mouseover="over">
            <dt>{{nav.tittle}}</dt>
            <dd
                v-for="(item,index) in nav.list"
                :key="index"
                :class="{active: kind == item.tab}"
                :data-type="item.tab"
            >{{item.text}}</dd>
            <dd class="all">
                <a href>
                    <span>全部</span>
                    <span class="iconfont icon-arrow-right"></span>
                </a>
            </dd>
        </dl>
    </div>
</template>

<script>
export default {
    data() {
        return {
            kind: "1",
        };
    },
    props: ["nav"],
    methods: {
        over(e) {
            let dom = e.target;
            let tagName = dom.tagName.toLowerCase();
            if (tagName != "dd") {
                return false;
            }
            this.kind = dom.getAttribute("data-type");
        },
    },
};
</script>

<style scoped lang=less>
.container {
    height: 44px;
    line-height: 44px;
    box-sizing: border-box;
    color: white;
    border-top-left-radius: 5px;
    border-top-right-radius: 5px;
    dl {
        height: 45px;
        &::after {
            content: "";
            display: block;
            clear: both;
            visibility: hidden;
        }
        dt {
            float: left;
            height: 44px;
            line-height: 44px;
            font-size: 18px;
            margin-left: 13px;
            margin-right: 10px;
            padding: 0 5px;
            box-sizing: border-box;
        }
        dd {
            float: left;
            cursor: pointer;
            position: relative;
            font-size: 14px;
            padding: 0 5px;
        }

        .active::after {
            position: absolute;
            content: "";
            border-right: 5px solid transparent;
            border-left: 5px solid transparent;
            border-bottom: 7px solid white;
            top: 37px;
            left: 0;
            right: 0;
            width: 2px;
            margin: auto;
        }
        .all {
            float: right;
            margin-right: 12px;
            height: 20px;
        }
    }
}
</style>