<template>
  <footer>
    <div class="power" v-show="!store.playerState">
      <span
        >&copy;&nbsp;2007&nbsp;-&nbsp;{{ fullYear }}&nbsp;
        <a href="https://www.wulintang.cn" target="_blank">南通伍林堂文化传播有限公司</a>&nbsp;版权所有
      </span>&nbsp;&amp;&nbsp;
      <!-- 站点备案 -->
      <a href="https://beian.miit.gov.cn" target="_blank"
        >苏ICP备2021008246号-9</a
      >&nbsp;
      <!-- 网案备案 -->
      <a href="http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=32061102000200" target="_blank"
        >苏公网安备32061102000200号</a
      >&nbsp;&amp;  
      <!-- 以下信息请不要修改哦 -->
      <span class="hidden"
        >Made&nbsp;by&nbsp;<a
          :href="config.github"
          target="_blank"
        >
          {{ config.author }}
        </a></span
      >&nbsp;&amp;
      <a href="http://www.atcpu.com/" target="_blank"
        >灯火互联网</a
      >
    </div>
    <div class="lrc" v-show="store.playerState">
      <music-one theme="filled" size="18" fill="#efefef" />
      <span class="lrc-text">
        {{ store.getPlayerLrc ? store.getPlayerLrc : "这句没有歌词" }}
      </span>
      <music-one theme="filled" size="18" fill="#efefef" />
    </div>
  </footer>
</template>

<script setup>
import { MusicOne } from "@icon-park/vue-next";
import { mainStore } from "@/store";
import config from "@/../package.json";
const store = mainStore();

let fullYear = new Date().getFullYear();
</script>

<style lang="scss" scoped>
footer {
  width: 100%;
  position: absolute;
  bottom: 0;
  left: 0;
  height: 46px;
  line-height: 46px;
  text-align: center;
  backdrop-filter: blur(10px);
  background: rgb(0 0 0 / 25%);
  z-index: 0;
  animation: fade;
  -webkit-animation: fade 0.5s;
  @media (max-width: 720px) {
    font-size: 0.85rem;
  }
  @media (max-width: 480px) {
    .hidden {
      display: none;
    }
  }
  .power {
    animation: fade;
    -webkit-animation: fade 0.3s;
  }
  .lrc {
    padding: 0 20px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    animation: fade;
    -webkit-animation: fade 0.3s;
    .lrc-text {
      margin: 0 8px;
      display: -webkit-box;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: 1;
      overflow: hidden;
      word-break: break-all;
    }
    .i-icon {
      width: 18px;
      height: 18px;
      display: inherit;
    }
  }
}
</style>
