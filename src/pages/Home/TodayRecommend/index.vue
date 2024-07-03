<template>
          <div class="today-recommend">
            <div class="py-container">
                <ul class="recommend">
                    <li class="clock">
                        <div class="time">
                            <img src= "../TodayRecommend/images/clock.png" />
                            <h3>今日推荐</h3>
                        </div>
                    </li>
                    <li class="banner">
                        <img src="../TodayRecommend/images/1.jpg" />
                    </li>
                    <li class="banner">
                        <img src="../TodayRecommend/images/2.jpg" />
                    </li>
                    <li class="banner">
                        <img src="../TodayRecommend/images/3.jpg" />
                    </li>
                    <li class="banner">
                        <img src="../TodayRecommend/images/4.jpg" />
                    </li>
                </ul>
            </div>
        </div>
</template>

<script>
export default {
    name:'TodayRecommend'
}
</script>

<style lang="less" scoped>
  .today-recommend {
        .py-container {
            width: 1200px;
            margin: 0 auto;

            .recommend {
                height: 230px;
                background-color: #eaeaea;
                margin: 10px 0;
                display: flex;

                .clock {
                    width: 16.67%;
                    background-color: #5c5251;
                    color: #fff;
                    font-size: 18px;
                    text-align: center;

                    .time {
                        padding: 60px 0;
                    }

                    h3 {
                        margin: 9px 0;
                        font-weight: 700;
                        font-size: 18px;
                        line-height: 30.06px;
                    }
                }

                .banner {
                    width: 20.83%;

                    img {
                        width: 100%;
                        height: 100%;
                        transition: all 400ms;

                        &:hover {
                            opacity: 0.5;
                        }
                    }
                }
            }
        }
    }
</style>