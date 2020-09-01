<template>
    <div>
        <myContainer class="movie-bar" :nav="movieTag" />
        <div class="slider">
            <div class="slider-content" :style="{left: place + 'px'}">
                <div class="movieTab" v-for="(item,index) in moviesOn" :key="index">
                    <a href>
                        <img :src="item.img" class="film-img" />
                        <img
                            src="//s0.meituan.net/bs/fe-web-meituan/25e6614/img/imax3d.png"
                            class="film-mark"
                            style="display: inline-block;"
                        />
                        <div class="film-info">
                            <div class="film-score">
                                <b>
                                    观众评
                                    <span>{{item.score}}</span>
                                </b>
                            </div>
                            <div class="film-name">{{ item.tittle }}</div>
                            <div class="buy-ticket">购票</div>
                        </div>
                    </a>
                </div>
            </div>
            <div class="btn btn-next" @click="nextPage()">
                <i class="el-icon-arrow-right" />
            </div>
            <div class="btn btn-pre" @click="prevPage()">
                <i class="el-icon-arrow-left" />
            </div>
        </div>
    </div>
</template>

<script>
import myContainer from "./container";
import axios from 'axios'
export default {
    data() {
        return {
            movieTag: "",
            moviesOn: "",
            moveDistance: 0,
            place: 0,
            distance: 1165,
            singleDistance: 20,
            loopTime: 10,
            page: 0,
            num: 1,
            savePlace: 0,
            backTo: undefined,
            nextTo: undefined,
        };
    },
    created() {
        axios.get('https://www.fastmock.site/mock/a7fdfe59948bf7e5e2764cd0b5e7ce30/meituan/api/movieType').then((response) => {
            this.movieTag = response.data.movieTag}),
        axios.get('https://www.fastmock.site/mock/a7fdfe59948bf7e5e2764cd0b5e7ce30/meituan/api/movie/on').then((response) => {
            this.moviesOn = response.data.moviesOn})
    },
    methods: {
        nextPage() {
            if (this.page < this.num) {
                this.page++;
                var vm = this;
                console.log(this.page);

                this.nextTo = setInterval(vm.next, vm.loopTime);
            }
        },
        prevPage() {
            if (this.page != 0) {
                this.page--;
                let vm = this;
                console.log(this.page);
                this.backTo = setInterval(vm.prev, vm.loopTime);
            }
        },
        next() {
            if (this.moveDistance < this.distance) {
                this.moveDistance += this.singleDistance;
                this.place -= this.singleDistance;
            } else {
                this.moveDistance = 0;
                this.place = this.savePlace - this.distance;
                this.savePlace = this.place;
                clearInterval(this.nextTo);
                console.log([this.moveDistance,this.place,this.savePlace])
            }
        },
        prev() {
            if (this.moveDistance < this.distance) {
                this.moveDistance += this.singleDistance;
                this.place += this.singleDistance;
            } else {
                this.moveDistance = 0;
                this.place = this.savePlace + this.distance;
                this.savePlace = this.place;
                clearInterval(this.backTo);
            }
        },
    },
    components: {
        myContainer,
    },
};
</script>

<style scoped lang=less>
.slider {
    overflow: hidden;
    position: relative;
    .slider-content {
        margin-left: 10px;
        margin-top: 1px;
        box-sizing: border-box;
        width: 10000px;
        position: relative;
        &::after {
            content: "";
            display: block;
            clear: both;
        }
        .movieTab {
            float: left;
            height: 297px;
            position: relative;
            margin-right: 19px;
            /* border: 1px solid black; */
            .film-img {
                border-radius: 4px;
            }
            .film-mark {
                position: absolute;
                left: -6px;
                top: 10px;
                height: 20px;
                box-shadow: 0 2px 6px 0 rgba(0, 0, 0, 0.2);
            }
            .film-info {
                position: absolute;
                bottom: 0px;
                width: 100%;
                height: 100px;
                color: white;
                border-bottom-left-radius: 4px;
                border-bottom-right-radius: 4px;
                background-image: linear-gradient(
                    -180deg,
                    rgba(0, 0, 0, 0) 0%,
                    rgba(29, 45, 55, 0.8) 99%
                );
                .film-score {
                    margin-top: 48px;
                    padding-left: 10px;
                    font-size: 12px;
                    span {
                        color: #fd9827;
                        font-size: 16px;
                    }
                }
                .film-name {
                    padding-left: 10px;
                    font-size: 16px;
                    font-weight: bold;
                    white-space: nowrap;
                    width: 7em;
                    overflow: hidden;
                    text-overflow: ellipsis;
                }
                .buy-ticket {
                    float: right;
                    position: relative;
                    top: -24px;
                    margin-right: 12px;
                    background: #ff4949;
                    border-radius: 100px;
                    font-size: 14px;
                    cursor: pointer;
                    padding: 2px 12px 2px 12px;
                }
            }
        }
    }
    &:hover > .btn {
        opacity: 0.8;
    }
    .btn {
        width: 40px;
        height: 40px;
        background: #333;
        position: absolute;
        z-index: 5px;
        top: 40%;
        border-radius: 50%;
        opacity: 0;
        transition: opacity 0.5s;
        transform: scale(0.95);
        cursor: pointer;
        text-align: center;

        i {
            color: #fff;
            font-size: 25px;
            font-weight: bold;
            line-height: 40px;
        }
    }
    .btn-next {
        right: 0px;
    }
    .btn-pre {
        left: 0px;
    }
}
</style>