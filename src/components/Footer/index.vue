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
      >
<component :is="'script'">
document.writeln("<div class=\'security-help-wrapper\'><div class=\'security-help\'><div class=\'sh-head\'><img src=\'https://www.wulintang.net/Public/Index/images/logo.png\'><span>安全漏洞<br>信息反馈</span></div><div class=\'sh-body\'><p>如果您发现伍林堂下属产品存在安全漏洞，欢迎将您所发现的漏洞信息提交到<a target=\'_blank\'href=\'http://www.wulintang.net/\'><em>伍林堂安全应急响应中心</em></a></p></div></div></div>");
document.writeln("<style type=text/css>.security-help-wrapper { padding: 2%; } .security-help { width:calc(100% - 40px); max-width:460px; margin:0 auto; display:flex; align-items:stretch; justify-content:center; color:#666; font-size:13px; } .security-help .sh-head {line-height: normal;width:114px; min-width:114px; display:flex; align-items:center; justify-content:center; padding:5px; color:#ffffff; background-color:#004c98; border:1px solid #004c98; user-select:none; } .security-help .sh-head img { width:28px; min-width:28px; margin-right:5px; display:block; height:auto; white-space:nowrap; } .security-help .sh-body { flex:1 1 auto; align-items:center; justify-content:center; padding:8px 10px; background-color:#fff; border:1px solid #004c98; color:#004c98; user-select:none; } .security-help .sh-body p { color: #004c98!important; margin-bottom: auto!important; line-height: inherit!important; font-size: inherit!important; } .security-help .sh-body em { display:inline-block; position:relative; font-style:normal; color:#004c98; white-space:nowrap; cursor:pointer; } .security-head .sh-body p a { text-decoration: none; color:#004c98; } @media (max-width:700px) { .security-help-wrapper { background-color:#fff; } .security-help .sh-body { font-size:10px; } .security-help .sh-head { width:110px; min-width:110px; font-size:12px; } .security-help .sh-head img { width:26px; min-width:26px; } .bkt { bottom:15px !important; } }</style>");
</component>
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
