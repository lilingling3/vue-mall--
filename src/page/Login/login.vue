<template>
  <div class="login v2">
      <div class="wrapper">
          <div class="dialog dialog-shadow">
              <div class="title" v-if="loginPage">
                  <h4>使用 Smartisan ID 登录官网</h4>
              </div>
              <div class="content" v-if="loginPage">
                  <ul class="common-form">
                      <li class="username border-1p">
                          <div class="input">
                              <input type="text" v-model="ruleForm.userName" placeholder="帐号">
                          </div>
                      </li>
                      <li>
                          <div class="input">
                              <input type="password" v-model="ruleForm.userPwd" @keyup.enter="login" placeholder="密码">
                          </div>
                      </li>
                      <li class="pr">
                         <span class="pa" style="top:0;left:0;color:#d4d4d4;">{{ruleForm.errMsg}}</span>
                         <a href="javascript:;" style="padding: 0 5px" @click="loginPage=false">注册 Smartisan ID</a>
                      </li>
                  </ul>
                  <!-- 登录 -->
                  <div>
                      <y-button text='登录' 
                      :classStyle="ruleForm.userPwd&& ruleForm.userName?'main-btn':'disabled-btn'"
                      @btnClick="login" style="margin: 0;width: 100%;height: 48px;font-size: 18px;line-height: 48px"></y-button>
                  </div>
              </div>
              <div class="registered" v-else>
                  <h4>注册 Smartisan ID</h4>
                  <div class="content" style="margin-top: 20px;">
                      <ul class="common-form">
                          <li class="username border-1p">
                            <div class="input">
                                <input type="text"
                                        v-model="registered.userName" placeholder="账号"
                                        @keyup="registered.userName=registered.userName.replace(/[^\w\.\/]/ig,'')">
                            </div>
                        </li>
                        <li>
                            <div class="input">
                                <input type="password"
                                        v-model="registered.userPwd"
                                        placeholder="密码">
                            </div>
                        </li>
                        <li>
                            <div class="input">
                                <input type="password"
                                        v-model="registered.userPwd2"
                                        placeholder="重复密码">
                            </div>
                        </li>
                      </ul>
                      <div>
                          <y-button
                            :classStyle="registered.userPwd&&registered.userPwd2&&registered.userName?'main-btn':'disabled-btn'"
                            text="注册"
                            style="margin: 0;width: 100%;height: 48px;font-size: 18px;line-height: 48px"
                            @btnClick="regist" >
                         </y-button>
                      </div>
                      <ul>
                         <li class="pa" style="left: 0;top: 0;margin: 0;color: #d44d44">{{registered.errMsg}}</li> 
                         <li style="text-align: center;line-height: 48px;margin-bottom: 0;">
                             <span>如果您已拥有 Smartisan ID，则可在此</span>
                             <a href="javascript:;" style="margin: 0 5px" @click="loginPage=true">登录</a>
                         </li>
                      </ul>
                  </div>
              </div>
          </div>
      </div>


  </div>
</template>

<script>
import YButton from '@/components/YButton'
export default {
  data(){
      return {
          loginPage: false,
          ruleForm: {
            userName: '',
            userPwd: '',
            errMsg: ''
          },
          registered: {
            userName: '',
            userPwd: '',
            userPwd2: '',
            errMsg: ''
        }
      }
  },
  methods:{
      login(){

      },
      regist(){

      }
  },
  components:{YButton}
}
</script>


<style lang="scss" scoped>
*{
    box-sizing: content-box
}
.login{
     overflow-x: hidden;
     overflow-y: hidden;
    .input{
        height: 50px;
        display: flex;
        align-items: center;
        input{
            font-size: 16px;
            width: 100%;
            height: 100%;
            padding: 10px 15px;
            box-sizing: border-box;
            border: 1px solid #cccccc;
            border-radius: 6px;
        }
    }
    .wrapper{
        background: url(/static/images/bg_9b9dcb65ff.png) repeat;
        background-size: 100px;
        min-height: 800px;
        min-width: 630px;
    }

}
.v2 .dialog{
    position: absolute;
    width: 450px;
    border: 1px solid #dadada;
    border-radius: 10px;
    top: 50%;
    left: 50%;
    margin-left: -225px;
    margin-top: -362px;
    .title{
        background: linear-gradient(#fff, #f5f5f5);
        // height: auto;
        overflow: visible;
        position: relative;
        background: url(/static/images/smartisan_4ada7fecea.png) no-repeat top center;
        background-size: 160px;
        height: 92px;
        margin: 23px 0 50px;
        padding: 75px 0 0;
        box-shadow: none;
        box-sizing: content-box;
        h4{
            padding: 0;
            text-align: center;
            color: #666;
            // border-bottom: 1px solid #dcdcdc;
            -webkit-box-shadow: none;
            -moz-box-shadow: none;
            box-shadow: none;
            position: absolute;
            bottom: 0;
            width: 100%;
            text-align:center;
            margin: 0;
            line-height: 1em;
            height: auto;
            color: #333;
            font-weight: 400;
        }
    }
    .content{
        padding: 0 40px 22px;
        height: auto;
        .common-form li{
            clear: both;
            margin-bottom: 15px;
            position: relative;
        }
    }
}

// 盒阴影
.dialog-shadow, .v2 .bbs .dialog-shadow, .v2 .dialog-shadow {
    -webkit-box-shadow: 0 9px 30px -6px rgba(0, 0, 0, .2), 0 18px 20px -10px rgba(0, 0, 0, .04), 0 18px 20px -10px rgba(0, 0, 0, .04), 0 10px 20px -10px rgba(0, 0, 0, .04);
    -moz-box-shadow: 0 9px 30px -6px rgba(0, 0, 0, .2), 0 18px 20px -10px rgba(0, 0, 0, .04), 0 18px 20px -10px rgba(0, 0, 0, .04), 0 10px 20px -10px rgba(0, 0, 0, .04);
    box-shadow: 0 9px 30px -6px rgba(0, 0, 0, .2), 0 18px 20px -10px rgba(0, 0, 0, .04), 0 18px 20px -10px rgba(0, 0, 0, .04), 0 10px 20px -10px rgba(0, 0, 0, .04);
  }

@media screen and (min-width: 737px), screen and (-webkit-max-device-pixel-ratio: 1.9) and (max-width: 736px) and (min-device-width: 737px){
    .wrapper{
        background: url(/static/images/con-bg_04f25dbf8e.jpg) repeat-x;
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
    }
    .dialog{
        background: url(/static/images/dialog-gray-bg.png) #fff bottom repeat-x;
        border-radius: 12px;
        // display: none;
        margin: -163px 0 0 -218px;
        width: 436px;
        position: fixed;
        left: 50%;
        top: 50%;
    }

    .dialog .title h4{
        // border-bottom: 1px solid #d1d1d1;
        box-shadow: 0 2px 6px #d1d1d1;
        color: #666;
        font-size: 20px;
        height: 61px;
        line-height: 61px;
        padding: 0 0 0 35px;
    }
}

.registered h4{
    padding: 0;
    text-align: center;
    color: #666;
    border-bottom: 1px solid #dcdcdc;
    -webkit-box-shadow: none;
    -moz-box-shadow: none;
    box-shadow: none;
    font-weight: 700;
    font-size: 20px;
    height: 60px;
    line-height: 60px;
}
</style>

