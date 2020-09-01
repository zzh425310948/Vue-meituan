<template>
    <div class="body">
        <div class="header">
            <div class="topBar">
                <topBar />
            </div>
            <searchBar />
        </div>
        <div class="mainlist">
            <mainList />
        </div>
        <div>
            <footNav />
        </div>
    </div>
</template>

<script>
import topBar from "@/components/topBar";
import searchBar from "@/components/searchBar";
import mainList from "@/components/mainList";
import footNav from "@/components/footNav";

export default {
    name: "",
    data() {
        return {};
    },
    methods: {},
    components: {
        topBar,
        searchBar,
        mainList,
        footNav,
    },
};
</script>

<style scoped lang=less>
.body {
    color: #666;
    background-color: #f8f8f8;
    div {
        width: 1190px;
        margin: 0 auto;
        box-sizing: border-box;
    }

    .header {
        width: 100%;
        height: 197px;
        background-color: #fff;
        box-shadow: 0 7px 27px 0 rgba(0, 0, 0, 0.1);
        .topBar {
            width: 100%;
            background-color: #f8f8f8;
        }
    }
}
</style>