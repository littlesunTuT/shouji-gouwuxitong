<template>
  <div class="swiper-container" ref="cur">
    <div class="swiper-wrapper">
      <div class="swiper-slide" v-for="carousel in list" :key="carousel.id">
        <img :src="carousel.imgUrl">
      </div>
    </div>
    <!-- 如果需要分页器 -->
    <div class="swiper-pagination"></div>

    <!-- 如果需要导航按钮 -->
    <div class="swiper-button-prev"></div>
    <div class="swiper-button-next"></div>
  </div>
</template>

<script>
import Swiper from 'swiper'
export default {
  name:'Carousel',
  props:['list'],
  watch: {
        list: {
            //立即监听:不管你数据有没有变化，上来立即监听一次
            //为什么watch监听不到list? 因为这个数据从来没有发生变化
            immediate: true,
            handler() {
                this.$nextTick(() => {
                    var mySwiper = new Swiper(
                        this.$refs.cur,
                        {
                            loop: true, // 循环模式选项
                            autoplay: {
                                delay: 3000, // 3秒切换一次
                                disableOnInteraction: false, // 用户操作后是否停止自动轮播
                            },
                            // 如果需要分页器
                            pagination: {
                                el: '.swiper-pagination',
                                //点击小圆圈的时候也切换图片
                                clickable: true
                            },

                            // 如果需要前进后退按钮
                            navigation: {
                                nextEl: '.swiper-button-next',
                                prevEl: '.swiper-button-prev',
                            },
                        }
                    );
                })
            }
        }
    }
}
</script>
<style>
    /* 自定义左右切换按钮样式 */
    .swiper-button-next,
    .swiper-button-prev {
      color:rgb(249, 100, 100);
    }

    /* 鼠标悬停时的样式 */
    .swiper-button-next:hover,
    .swiper-button-prev:hover {
      background-color:rgb(194, 196, 196); /* 悬停时的背景颜色 */
    }
  </style>