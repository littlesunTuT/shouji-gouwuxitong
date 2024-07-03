<template>
    <div class="rank">
            <div class="tab">
                <div class="tab-tit clearfix">
                    <a href="javascript:;" class="on">
                        <p class="img">
                            <i></i>
                        </p>
                        <p class="text">热卖排行</p>
                    </a>
                    <a href="javascript:;" class="two">
                        <p class="img">
                            <i></i>
                        </p>
                        <p class="text">特价排行</p>
                    </a>
                    <a href="javascript:;" class="two">
                        <p class="img">
                            <i></i>
                        </p>
                        <p class="text">新品排行</p>
                    </a>
                </div>

            </div>
            <div class="content">
                <ul>
                    <li>
                        <div class="img-item">
                            <p class="tab-pic">
                                <a href="#">
                                    <img src="../Rank/images/1.jpg" />
                                </a>
                            </p>
                            <div class="tab-info">
                                <div class="info-title">
                                    <a href="#">华为（HUAWEI）遥遥领先</a>
                                </div>
                                <p class="info-price">定金：¥6199.00起</p>
                            </div>
                        </div>
                        <div class="img-item">
                            <p class="tab-pic">
                                <a href="#">
                                    <img src="../Rank/images/2.jpg" />
                                </a>
                            </p>
                            <div class="tab-info">
                                <div class="info-title">
                                    <a href="#">小米14 徕卡光学镜头 光影猎人900  小米手机<br>红米手机 5G</a>
                                </div>
                                <p class="info-price">定金：¥4599.00起</p>
                            </div>
                        </div>
                        <div class="img-item">
                            <p class="tab-pic">
                                <a href="#">
                                    <img src="../Rank/images/3.jpg" />
                                </a>
                            </p>
                            <div class="tab-info">
                                <div class="info-title">
                                    <a href="#">Apple 苹果 iphone 15 苹果 iPhone 15Plus <br>灵动岛手机 全国联保</a>
                                </div>
                                <p class="info-price">定金：¥6879.00起</p>
                            </div>
                        </div>
                        <div class="img-item">
                            <p class="tab-pic">
                                <a href="#">
                                    <img src="../Rank/images/4.jpg" />
                                </a>
                            </p>
                            <div class="tab-info">
                                <div class="info-title">
                                    <a href="#">vivo iQOO 12  第三代骁龙 8 自研电竞芯片Q1 大底主摄潜望式长焦 5G手机</a>
                                </div>
                                <p class="info-price">定金：¥3999.00起</p>
                            </div>
                        </div>
                    </li>
                </ul>
            </div>
    </div>
</template>

<script>
export default {
    name:'Rank'
}
</script>

<style lang="less" scoped>
 img {
    width: 100%;
    height: 100%;
    transition: all 400ms;

    &:hover {
        opacity: 0.5;
    }
}
    .rank {
        width: 1200px;
        margin: 0 auto;

        .tab {
            margin: 0 auto;
            overflow: hidden;
            width: 312px;

            .tab-tit {
                text-align: center;

                a {
                    display: block;
                    padding: 0 18px;
                    float: left;
                    text-decoration: none;
                    font-size: 16px;
                    color: #343333;
                    &:hover{
                        opacity: 0.6;
                    }
                    p {
                        margin: 5px 0;
                    }

                    .img {
                        i {
                            width: 35px;
                            height: 35px;
                            display: block;
                            background: url(../Rank/images/bg0.png);
                            margin-left: 10px;
                        }
                    }

                    .text {
                        line-height: 28px;
                    }
                }

                .on {
                    color: #e60012;

                    .img {
                        i {
                            background-position: -35px 0;
                        }
                    }
                }
            }
        }

        .content {
            overflow: hidden;
            padding: 10px;

            ul {
                li {
                    overflow: hidden;
                    list-style: none;
                    line-height: 18px;

                    .img-item {
                        border: 1px solid #e1251b;
                        width: 269px;
                        float: left;
                        overflow: hidden;
                        margin: 0 12px 10px;
                        background: #fff;

                        .tab-pic {
                            width: 230px;
                            height: 210px;
                            overflow: hidden;
                            text-align: center;
                            margin: 5px auto 18px;

                            a {
                                img {
                                    width: 200px;
                                    height: 200px;
                                }
                            }
                        }

                        .tab-info {
                            background: #fafafa;

                            .info-title {
                                height: 50px;
                                line-height: 28px;
                                overflow: hidden;
                                margin: 0 auto;
                                padding-left: 10px;

                                a {
                                    color: #333;
                                    text-decoration: none;
                                }
                            }

                            .info-price {
                                font-size: 20px;
                                color: #e1251b;
                                height: 35px;
                                padding-left: 10px;
                                display: block;
                                line-height: 24px;
                                margin: 10px auto 0;
                            }
                        }
                    }
                }
            }
        }
    }
</style>