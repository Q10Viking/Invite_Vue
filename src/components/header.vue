<template>
  <div class="header">
    <img class="userinfo_avatar" :src="userInfo.avatarUrl ? userInfo.avatarUrl : userInfodefault.avatarUrl">
    <p class="userinfo_nickname">{{userInfo.nickName ? userInfo.nickName : userInfodefault.nickName}}</p>
    <p class="title">的邀请函</p>
  </div>
</template>

<script type="text/ecmascript-6">
  import store from '@/utils/store'
  export default {
    data () {
      return {
        userInfodefault: { avatarUrl: '/static/avatar-default.png', nickName: '我的' } // 默认值
      }
    },
    computed: {
      userInfo () {
        return store.state.userInfo // vuex状态改变
      }
    },
    mounted () {
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .header
    width 100%
    height auto
    color #fff
    .userinfo_avatar
      display block
      margin 0 auto 15px
      width 128px
      height 128px
      border-radius 50%
    .userinfo_nickname
      text-align center
      font-size 40px
    .title
      text-align center
      font-size 20px
</style>
