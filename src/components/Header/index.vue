<template>
  <div>
    <header class="header">
            <!-- 头部的第一行 -->
            <div class="top">
                <div class="container">
                    <div class="loginList">
                        <p>星期八欢迎您！</p>
                        <!-- 没有用户名未登陆 -->
                        <p v-if="!userName">
                            <span>请</span>
                            <router-link to="/login" style="color: red;">登录</router-link>
                            <router-link class="register" to="/register" style="color: red;">免费注册</router-link>
                        </p>
                        <!-- 登陆了 -->
                        <p v-else>
                            <a>{{userName}}</a>
                            <a class="register" @click="logout">退出登录</a>
                        </p>
                    </div>
                    <div class="typeList">
                        <router-link to="/center/myorder">我的订单</router-link>
                        <router-link to="/shopcart">我的购物车</router-link>
                        <a href="###">我的星期八</a>
                        <a href="###">星期八会员</a>
                        <a href="###">企业采购</a>
                        <a href="###">关注星期八</a>
                        <a href="###">合作招商</a>
                        <a href="###">商家后台</a>
                    </div>
                </div>
            </div>
            <!--头部第二行 搜索区域-->
            <div class="bottom">
                <h1 class="logoArea">
                    <router-link class="logo" to="/home">
                        <img src="../Header/image/phone.png" alt="">
                    </router-link>
                </h1>
                <div class="searchArea">
                    <form action="###" class="searchForm">
                        <input 
                        type="text" 
                        id="autocomplete" 
                        class="input-error input-xxlarge" 
                        v-model="keyword"
                        />
                        <button class="sui-btn btn-xlarge btn-danger" type="button" @click="goSearch">搜索</button>
                    </form>
                </div>
            </div>
    </header>
  </div>
</template>

<script>
export default {
    name:'',
    data() {
        return {
            keyword:''
        }
    },
    methods: {
        goSearch() {
            //路由传递参数：
            //第一种:字符串形式
            // this.$router.push('/search/'+this.keyWord + '?k='+this.keyWord.toUpperCase())
            //第二种:模板字符串
            //this.$router.push(`/search/${this.keyWord}?k=${this.keyWord.toUpperCase()}`)
            //第三种:对象
            if (this.$route.query) {
                let location = { name: 'search', params: { keyword: this.keyword || undefined } };
                location.query = this.$route.query;
                this.$router.push(location);
            }
        },
        //退出登录
        logout(){
           try {
            this.$store.dispatch('userLogout');
            //退出登录，回到首页
            this.$router.push('/home')
           } catch (error) {
            alert(error.message)
           } 
        }
    },
    mounted() {
        //通过全局事件总线清除关键字
        this.$bus.$on("clear",()=>{
            this.keyword = '';
        })
    },
    computed: {
        //用户名信息
        userName(){
            return this.$store.state.user.userInfo.name;
        }
    }
}
</script>

<style lang="less" scoped>
  .header {
        &>.top {
            background-color: #eaeaea;
            height: 60px;
            line-height: 30px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 16px;

            .container {
                width: 1200px;
                margin: 0 auto;
                overflow: hidden;

                .loginList {
                    float: left;

                    p {
                        float: left;
                        margin-right: 10px;

                        .register {
                            border-left: 1px solid #b3aeae;
                            padding: 0 5px;
                            margin-left: 5px;
                            color: red;
                           
                        }
                        a:hover{
                            text-decoration: underline;
                            cursor: pointer;
                        }
                    }
                }

                .typeList {
                    float: right;
                    

                    a {
                        padding: 0 10px;
                        color:rgb(39, 38, 38);
                        text-decoration: none;
                        &+a {
                            border-left: 1px solid #b3aeae;
                        }
                    }
                    a:hover{
                        color: red;
                    }

                }

            }
        }

        &>.bottom {
            width: 1200px;
            margin: 0 auto;
            overflow: hidden;

            .logoArea {
                float: left;

                .logo {
                    img {
                        width: 175px;
                        margin: 0px 20px;
                    }
                }
            }

            .searchArea {
                float: right;
                margin-top: 70px;

                .searchForm {
                    overflow: hidden;

                    input {
                        box-sizing: border-box;
                        width: 490px;
                        height: 36px;
                        padding: 0px 4px;
                        border: 2px solid #ea4a36;
                        float: left;

                        &:focus {
                            outline: none;
                        }
                    }

                    button {
                        height: 36px;
                        width: 68px;
                        background-color: #ea4a36;
                        border: none;
                        color: #fff;
                        float: left;
                        cursor: pointer;
                        font-size: larger;
                        &:focus {
                            outline: none;
                        }
                        &:hover{
                            opacity: 0.8;
                        }
                    }
                }
            }
        }
    }
</style>