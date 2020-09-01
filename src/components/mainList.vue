<template>
    <div class="main-list">
        <div class="show-bar">
            <showBar />
        </div>
        <div class="movies">
            <movies />
        </div>
        <div class="hotel">
            <hotel />
        </div>
        <div class="guess">
            <guess />
        </div>
        <div class="bottom-nav">
            <bottomNav /> 
        </div>
    </div>
</template>

<script>
import showBar from "./main/showBar"
import movies from "./main/movies"
import hotel from "./main/hotel"
import guess from "./main/guess"
import bottomNav from "./main/bottomNav"

export default {
    data() {
        return {
            
        }
    },
    components: {
        showBar,
        movies,
        hotel,
        guess,
        bottomNav
    }
};
</script>

<style scoped lang=less>
.main-list {
    > div {
        margin-top: 40px;
        box-sizing: border-box;
        /* border: 1px solid black; */
    }
    .show-bar {
        margin-top: 10px;
        height: 417px;
    }
}
</style>