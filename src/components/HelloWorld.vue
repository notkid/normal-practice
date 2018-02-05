<template>
  <div class="hello">
    <div class="header">
      headerheaderheaderheaderheaderheader
      headerheaderheaderheaderheaderheader
      headerheaderheaderheaderheaderheader
      headerheaderheaderheaderheaderheader
      headerheaderheaderheaderheaderheader
      headerheaderheaderheaderheaderheader
      headerheaderheaderheaderheaderheader
      headerheaderheaderheaderheaderheader
      headerheaderheaderheaderheaderheader
      headerheaderheaderheaderheaderheader
    </div>
    <div class="section">
      section
      <router-link to="/chat" class="router-link-logo">
        跳转到聊天页面
      </router-link>
    </div>
    <div class="footer">
      footerfooterfooterfooterfooterfooter
      footerfooterfooterfooterfooterfooter
      footerfooterfooterfooterfooterfooter
      footerfooterfooterfooterfooterfooter
      footerfooterfooterfooterfooterfooter
      footerfooterfooterfooterfooterfooter
      footerfooterfooterfooterfooterfooter
      footerfooterfooterfooterfooterfooter
      footerfooterfooterfooterfooterfooter
      footerfooterfooterfooterfooterfooter
      footerfooterfooterfooterfooterfooter
      footerfooterfooterfooterfooterfooter
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style scoped lang="less">
// 这里没有去特意写兼容浏览器的代码， postcss 打包时会自动加上
.hello {
  height: 100%;
  display: flex;
  flex-direction: column;
  .header {
    background-color: blue;
    overflow-wrap: break-word;
  }
  .section {
    background-color: red;
    height: 100%;
  }
  .footer {
    background-color: yellow;
    overflow-wrap: break-word;
  }
}
</style>
