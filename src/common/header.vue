<template>
  <div class="header-box">
      <div>
          <header class="w">
              <div class="w-box">
                  <div class="nav-logo">
                      <h1>
                          <router-link to="/" title="锤子科技官网">Smartisan</router-link>
                      </h1>
                  </div>
                  <div class="right-box">
                      <div class="nav-list">
                            <router-link to="goods">全部商品</router-link>
                            <router-link to="/">坚果 Pro</router-link>
                            <router-link to="/">Smartisan M1 / M1L</router-link>
                            <router-link to="/">Smartisan OS</router-link>
                            <router-link to="/">欢喜云</router-link>
                            <router-link to="/">应用下载</router-link>
                            <router-link to="/">官方论坛</router-link>
                      </div>
                      <div class="nav-aside" ref="aside">
                          <div class="user pr">
                               <router-link to="user">个人中心</router-link>
                               <!-- 用户信息显示 -->
                               <div class="nav-user-wrapper pa" >
                                   <div class="nav-user-list">
                                       <ul>
                                           <!-- 头像 -->
                                           <li class="nav-user-avatar">
                                               <div>
                                                   <span class="avatar"></span>
                                               </div>
                                               <p class="name"></p>
                                           </li>

                                           <li>
                                                <router-link to="/user/orderList">我的订单</router-link>
                                            </li>
                                            <li>
                                                <router-link to="/user/information">账号资料</router-link>
                                            </li>
                                            <li>
                                                <router-link to="/user/addressList">收货地址</router-link>
                                            </li>
                                            <li>
                                                <router-link to="/user/support">售后服务</router-link>
                                            </li>
                                            <li>
                                                <router-link to="/user/coupon">我的优惠</router-link>
                                            </li>


                                            <li>
                                                <a href="javascript:;" >退出</a>
                                            </li>
                                       </ul>
                                   </div>
                               </div>
                          </div>
                          <div class="shop pr" ref="positionMsg">
                              <router-link to="cart"></router-link>
                              <span class="cart-num">
                                  <i class="num"></i>
                              </span>
                              <!-- 购物车显示 -->
                              <div class="nav-user-wrapper pa active">
                                  <div class="nav-user-list">
                                      <div class="full">
                                          <!-- 购物车列表 -->
                                          <div class="nav-cart-items">
                                              <ul>
                                                  <li class="clearfix"></li>
                                              </ul>
                                          </div>
                                      </div>
                                      <div style="height: 313px;text-align: center" class="cart-con">
                                          <p>你的购物车竟然是空的!</p>
                                      </div>
                                  </div>
                              </div>
                          </div>
                      </div>
                  </div>
              </div>
          </header>
          <slot name="nav">
            <div class="nav-sub">
                <div class="nav-sub-bg"></div>
                <div class="nav-sub-wrapper">
                    <div class="w">
                        <ul class="nav-list">
                            <li>
                                <router-link to="/">首页</router-link>
                            </li>
                            <li>
                                <router-link to="/goods">全部商品</router-link>
                             </li>
                        </ul>
                        <div></div>
                    </div>
                </div>
            </div>
          </slot>
      </div>
  </div>
</template>

<script>
export default {
  
}
</script>
<style lang="scss">
@import "../assets/style/theme";
@import "../assets/style/mixin";
.header-box{
    background: $head-bgc;
    background-image: -webkit-linear-gradient(#000, #121212);
    background-image: linear-gradient(#000, #121212);
    width: 100%;
}

header{
    height: 100px;
    z-index: 30;
    position: relative;
}
.w-box{
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 100%;
    position: relative;
    h1{
        display: flex;
        height: 100%;
        align-items: center;
        //表示第一个
        >a{
            background: url(/static/images/global-logo-red@2x.png) no-repeat ;
            background-size: cover;
            display: block;
            @include wh(50px,40px);
            text-indent: -9999px; // 字体隐藏
            background-position: 50% 0;
        }
    }
    .nav-list{
        display: flex;
        justify-content: center;
        align-items: center;
        margin-right: 22px;
        a{
            color: #c8c8c8;
            display: block;
            font-size: 14px;
            padding: 0 25px;
            &:hover{
                color: #ffffff;
            }
        }
    }
    .nav-aside{
        position: relative;
        &:before{
            background: #333;
            background: hsla(0, 0%, 100%, .7);
            content: '';
            @include wh(1px, 13px);
            position: absolute;
            left: 0;
            top: 4px;
            overflow: hidden;
        }
    }
    .right-box{
        display: flex;
    }
    .nav-aside {
      display: flex;
    }
    // 用户
    .user{
        margin-left: 41px;
        width: 36px;
        &:hover{
            a:before{
                background-position: -5px 0;
            }
            .nav-user-wrapper{
                top:18px;
                visibility: visible;
                opacity: 1;
                -webkit-transition: opacity .15s ease-out;
                transition: opacity .15s ease-out;
             }
        }
        >a{
            position: relative;
            @include wh(36px, 20px);
            display: block;
            text-indent: -9999px;
            &:before{
                content: '';
                position: absolute;
                left: 8px;
                top: 0;
                @include wh(20px);
                background: url(/static/images/account-icon@2x.32d87deb02b3d1c3cc5bcff0c26314ac.png) -155px 0;
                background-size: 240px 107px;
                transition: none;
            }
        }
        // 第二li后面所有的
        li+li{
            text-align: center;
            position: relative;
            border-top: 1px solid #f5f5f5;
            line-height: 44px;
            height: 44px;
            color: #616161;
            font-size: 12px;
            &:hover{
                background: #fafafa;
            }
            a{
                display: block;
                color: #616161;
            }
        }
        // 下拉框
        .nav-user-wrapper{
            width: 168px;
            transform: translateX(-50%);
            left: 50%;
        }
        .nav-user-list{
            width: 168px;
            &:before{
                left: 50%;
            }
        }
        // 头像
        .nav-user-avatar{
            >div{
                position: relative;
                margin: 0 auto 8px;
                @include wh(46px);
                text-align: center;
                // 内部阴影 的圆框
                &:before{
                    content: '';
                    position: absolute;
                    left: 0;
                    right: 0;
                    top: 0;
                    bottom: 0;
                    border-radius: 50%;
                    box-shadow: inset 0 0 0 1px rgba(0, 0, 0, .06);
                }
                .avatar{
                    display: block;
                    border-radius: 50%;
                    @include wh(100%);
                    background-repeat: no-repeat;
                    background-size: contain;
                }
            }

            .name{
                margin-bottom: 16px;
                font-size: 12px;
                line-height: 1.5;
                text-align: center;
                color: #757575;
            }
        }
        
    }

    .shop{
        position: relative;
        // float: left;
        margin-left: 21px;
        width: 61px;
        z-index: 99;
        &:hover{
            a:before{
                content: '';
                background-position: 0 -22px;
            }
            .nav-user-wrapper.active{
                top: 18px;
                visibility: visible;
                opacity: 1;
                -webkit-transition: opacity .15s ease-out;
                transition: opacity .15s ease-out;
            }
        }
        >a{
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            right: 0;
            display: block;
            z-index: 1;
            &:before{
                display: block;
                @include wh(30px, 100%);
                content: '';
                background: url(/static/images/account-icon@2x.32d87deb02b3d1c3cc5bcff0c26314ac.png) 0 0;
                background-size: 240px 107px;
                background-position: -150px -22px;
            }
        }
        .cart-num{
            position: relative;
            display: block;
            margin-left: 31px;
            margin-top: -1px;
            text-indent: 0;
            line-height: 20px;
            i{
                background: #eb746b;
                background-image: -webkit-linear-gradient(#eb746b, #e25147);
                background-image: linear-gradient(#eb746b, #e25147);
                box-shadow: inset 0 0 1px hsla(0, 0%, 100%, .15), 0 1px 2px hsla(0, 0%, 100%, .15);
                text-align: center;
                font-style:normal;
                display: inline-block;
                @include wh(20px);
                line-height: 20px;
                border-radius: 10px;
                color: #ffffff;
                font-size: 12px;
            }
        }
        // 购物车
        .nav-user-wrapper{
            right: 0;
            width: 360px;
            .nav-user-list{
                &:before{
                    right: 34px;
                }
                padding: 0;
                width: 100%;
                .full{
                    border-radius: 8px;
                    overflow: hidden;
                }
            }
        }
    }
}
// 用户信息弹出
.nav-user-wrapper{
    position: absolute;
    z-index: 30;
    padding-top: 18px;
    opacity: 0;
    visibility: hidden;
    top: -3000px;
    .nav-user-list{
        position: relative;
        padding-top: 20px;
        background: #fff;
        border: 1px solid #d6d6d6;
        border-color: rgba(0, 0, 0, .08);
        border-radius: 8px;
        box-shadow: 0 20px 40px rgba(0, 0, 0, .15);
        z-index: 10;
        &:before{
            position: absolute;
            content: '';
            background: url(/static/images/account-icon@2x.32d87deb02b3d1c3cc5bcff0c26314ac.png) no-repeat -49px -43px;
            background-size: 240px 107px;
            @include wh(20px, 8px);
            top: -8px;
            margin-left: -10px;
        }
    }
}
// 子导航
.nav-sub{
    position: relative;
    z-index: 20;
    height: 90px;
    background: #f7f7f7;
    box-shadow: 0 2px 4px rgba(0, 0, 0, .04);
    .nav-sub-wrapper{
        padding: 31px 0;
        height: 90px;
        position: relative;
        .w{
            display: flex;
            justify-content: space-between;
            .nav-list{
                height: 28px;
                line-height: 28px;
                display: flex;
                align-items: center;
                height: 100%;
                li:first-child{
                    padding-left: 0;
                    a{
                        padding-left: 10px
                    }
                }
                li{
                    position: relative;
                    float: left;
                    padding-left: 2px;
                    a{
                        display: block;
                        padding: 0 20px;
                        color: #666;
                    }
                }
                li:before{
                    content: '';
                    position: absolute;
                    top: 13px;
                    width: 2px;
                    height: 2px;
                    background: #bdbdbd;
                }
                li:first-child:before{
                    left: 0;
                }
                li:last-child:before{
                    left: 13px;
                }
            }
        }

    }
}
// 空购物车
.cart-con{
    text-align: center;
    position: relative;
    p{
        padding-top: 185px;
        color: #333333;
        font-size: 16px;
    }
    &:before{
        position: absolute;
        content: '';
        width: 76px;
        height: 62px;
        background: url("/static/images/cart-empty-new.png") no-repeat;
        background-size: cover;
        transform: translate(-50%,-70%);
        left: 50%;
        top: 50%;
    }
}
</style>


