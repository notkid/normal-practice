<style scoped>
  .container {
    width: 100%;
    height: 100%;
    z-index: 100;
    position: fixed;
    left: 0;
    top: 0;
    overflow: hidden;
  }

  .window {
    box-shadow: 1px 1px 20px -5px #000;
    min-width: 400px;
    background: #F5F5F5;
    margin: 0 auto;
    overflow: hidden;
    padding: 0;
    height: 100%;
    position: relative;
    z-index: 101;
  }

  .title {
    background: #5293CF;
    text-align: center;
    color: #fff;
    width: 100%;
    height: 50px;
    line-height: 50px;
    font-size: 14px;
  }

  .message {
    padding: 10px 15px;
    background-color: #F5F5F5;
  }

  .message li {
    margin-bottom: 15px;
    left: 0;
    position: relative;
    display: block;
  }

  .message .time {
    margin: 10px 0;
    text-align: center;
  }

  .message .text {
    display: inline-block;
    position: relative;
    padding: 0 10px;
    max-width: calc(100% - 75px);
    min-height: 35px;
    line-height: 2.1;
    font-size: 15px;
    padding: 6px 10px;
    text-align: left;
    word-break: break-all;
    background-color: #fff;
    color: #000;
    border-radius: 4px;
    box-shadow: 0px 1px 7px -5px #000;
  }

  .message .avatar {
    float: left;
    margin: 0 10px 0 0;
    border-radius: 3px;
    background: #fff;
  }

  .message .time>span {
    display: inline-block;
    padding: 0 5px;
    font-size: 12px;
    color: #fff;
    border-radius: 2px;
    background-color: #DADADA;
  }

  .message .system>span {
    padding: 4px 9px;
    text-align: left;
  }

  .message .text:before {
    content: " ";
    position: absolute;
    top: 9px;
    right: 100%;
    border: 6px solid transparent;
    border-right-color: #fff;
  }

  .message .self {
    text-align: right;
  }

  .message .other {
    text-align: left;
  }

  .message .self .text {
    background-color: #5293CF;
  }

  .message .self .text:before {
    right: inherit;
    left: 100%;
    border-right-color: transparent;
    border-left-color: #5293CF;
  }

  .message .image {
    max-width: 200px;
  }
</style>

<template>
  <div class="container" :style="{backgroundColor: wrapBg}">
    <div class="window" :style="{maxHeight: maxHeight + 'px', width: width +'px'}">
      <div class="title" v-if="dataArray && dataArray.length>0">
        <p v-text="contactNickname"></p>
      </div>
      <!-- main -->
      <div class="container-main" v-if="dataArray && dataArray.length>0" :style="{maxHeight: maxHeight-50 + 'px'}">
        <div class="message">
          <ul>
            <li v-for="(message, index) in dataArray" :key="message.id" :class="message.direction==2?'an-move-right':'an-move-left'">
              <p class="time">
                <span v-text="message.ctime"></span>
              </p>
              <p class="time system" v-if="message.type==10000">
                <span v-html="message.content"></span>
              </p>
              <div :class="'main' + (message.direction==2?' self':' other')" v-else>
                <div class="text" v-if="message.type==1">
                  {{message.content}}
                </div>
                <div class="text" v-else-if="message.type==2">
                  <img :src="message.content" class="image" alt="聊天图片">
                </div>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  /*eslint-disable */
  export default {
    name: "wxChat",

    props: {
      contactNickname: {
        type: String,
        default: 'Mystic Faces'
      },

      data: {
        type: Array,
        required: true
      },

      width: {
        type: Number,
        default: 450,
      },

      wrapBg: {
        type: String,
        default: '#efefef'
      },

      maxHeight: {
        type: Number,
        default: 700
      }
    },

    data() {
      return {
        dataArray: []
      }
    },

    created() {
      this.initData();
    },

    methods: {
      initData() {
        this.dataArray = this.dataArray.concat(this.data);
      }
    }
  }
</script>