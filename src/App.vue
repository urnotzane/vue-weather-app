<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {};
  }
};
</script>

<style lang="scss">
// rem 单位换算：定为 75px 只是方便运算，750px-75px、640-64px、1080px-108px，如此类推
$vw_fontsize: 75; // iPhone 6尺寸的根元素大小基准值
@function rem($px) {
  @return ($px / $vw_fontsize) * 1rem;
}
// 根元素大小使用 vw 单位
$vw_design: 750;
html {
  height: 100vh;
  font-size: ($vw_fontsize / ($vw_design / 2)) * 100vw;
  // 同时，通过Media Queries 限制根元素最大最小值
  @media screen and (max-width: 320px) {
    font-size: 64px;
  }
  @media screen and (min-width: 540px) {
    font-size: 108px;
  }
  $color_n: #7085b6 0%, #def3f8 100%;
  background: -webkit-linear-gradient(bottom, $color_n);
  background: -o-linear-gradient(bottom, $color_n);
  background: -moz-linear-gradient(bottom, $color_n);
  background-image: linear-gradient(to bottom, $color_n); //凌晨
  color: #fff;
  // background-image: linear-gradient(to bottom, $color_n); //凌晨
  // background-image: linear-gradient(to bottom, #ace0f9 0%, #fff1eb 100%);//清晨
  //  background-image: linear-gradient(to bottom, #a8edea 0%, #fed6e3 100%);//上午
  // background-image: linear-gradient(to bottom, #96e6a1 0%, #fbfcdb 100%);//中午
  // background-image: linear-gradient(to bottom, #2CD8D5 0%, #FFBCCC 100%);//下午
  //  background-image: linear-gradient(to bottom, #d5dee7 0%, #ffafbd 0%, #c9ffbf 100%);//黄昏
  // background-image: linear-gradient(to bottom, #6f86d6 50%, #48c6ef 100%);//晚上
  // background-image: linear-gradient(to bottom, #304352 0%, #d7d2cc 100%);//深夜
}
// body 也增加最大最小宽度限制，避免默认100%宽度的 block 元素跟随 body 而过大过小
body {
  max-width: 540px;
  min-width: 320px;
  margin: 0 auto;
  font-size: 0.18rem;
  #app {
    position: relative;
    height: 100vh;
    box-sizing: border-box;
  }
}
</style>

