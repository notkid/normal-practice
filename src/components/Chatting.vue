<template>
<Chat 
  :data="Data"
  contactNickname="在线客服"
  :width="420">
</Chat>
</template>

<script>
/*eslint-disable */
import Chat from './Chat.vue'

export default {
  name: 'app',
  data () {
    return {
      Data: [{
        direction: 1,
        id: 1,
        type: 1,
        content: '你好!这里是今日旅游的在线客服，请问有什么可以帮到你您吗',
        ctime: new Date().toLocaleString()
      },
      {
        direction: 2,
        id: 2,
        type: 1,
        content: '你好，我想改签下机票',
        ctime: new Date().toLocaleString()
      },
      {
        direction: 1,
        id: 3,
        type: 1,
        content: '好的，帮您查一下',
        ctime: new Date().toLocaleString()
      },
      {
        direction: 2,
        id: 5,
        type: 1,
        content: '还有我想问，为什么这个订单失败了',
        ctime: new Date().toLocaleString()
      },
      {
        direction: 2,
        id: 4,
        type: 2,
        content: '/static/payment.png',
        ctime: new Date().toLocaleString()
      }]
    }
  },
  components:{Chat}
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
}

</style>
