<template>
<div class="qf-user" @scroll='pageScroll'>

  <div class="user-info">
    <div class="ui-tip">管理我的账户</div>
    <div class="ui-box">
      <img src="//storage.360buyimg.com/i.imageUpload/78696168616966656e673131313131353636373937323133333639_big.jpg" alt="">
      <div>
        <div>张三</div>
        <div>zhangsan</div>
      </div>
    </div>
  </div>

  <div>
    <van-cell-group>
      <van-cell title="收货地址管理" value="管理我的收货地址" is-link />
      <van-cell title="账户与安全" value="密码实名认证等管理" is-link />
    </van-cell-group>
  </div>

  <div>
    <van-grid direction="horizontal" :column-num="3">
      <van-grid-item text="意见反馈">
        <template #icon>
          <img class='icon' :src="$img.u1Icon" alt="">
        </template>
      </van-grid-item>
      <van-grid-item text="京东客户端">
        <template #icon>
          <img class='icon' :src="$img.u2Icon" alt="">
        </template>
      </van-grid-item>
      <van-grid-item text="退出登录">
        <template #icon>
          <img class='icon' :src="$img.u3Icon" alt="">
        </template>
      </van-grid-item>
    </van-grid>
  </div>

  <QfTabbar />
</div>
</template>

<script>
import { QfTabbar } from '@/components/'
export default {
  components: {
    QfTabbar
  },
  // 局部路由守卫
  // 组件尚未实例化，无法访问this、声明式变量
  beforeRouteEnter(to, from, next) {
    // next('/login')
    next()
  },
  methods: {
    pageScroll(e) {
      console.log('e', e)
    }
  }
}
</script>

<style lang="scss" scoped>
.qf-user {
  .user-info{
    .ui-tip {
      line-height: 1.33rem;
      font-size: .53rem;
      padding-left: .33rem;
      box-sizing: border-box;
      background: white;
    }
    .ui-box {
      width: 9.47rem;
      height: 2.4rem;
      overflow: hidden;
      border: .03rem solid red;
      box-sizing: border-box;
      margin: 0 auto;
      border-radius: .11rem;
      background: white;
      &>img {
        float: left;
        width: 1.2rem;
        height: 1.2rem;
        border-radius: 50%;
        margin-top: .6rem;
        margin-left: .47rem;
      }
      &>div {
        line-height: .6rem;
        font-size: .43rem;
        float: left;
        margin-top: .6rem;
        margin: .47rem;
      }
    }
  }
  .icon {
    display: inline-block;
    width: .53rem;
    height: .48rem;
  }
}
</style>
