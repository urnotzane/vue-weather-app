<template>
  <div id="app">
    <div class="switch-dot">
      <div class="dot-item"></div>
      <div class="dot-item"></div>
      <div class="dot-item"></div>
    </div>
    <div class="switch-body">
      <div class="weather-header"></div>
      <div class="weather-body">
        <div class="weather-brief">
          <div class="brief-city brief-item">
            广州
          </div>
          <div class="brief-tempreture brief-item">
            <span>22°</span>
            <span>晴</span>
          </div>
          <div class="brief-detail brief-item">
            <div class="detail-item">
              <div>14:58</div>
              <div>日出三竿</div>
            </div>
            <div class="detail-item">
              <div>15°~24°</div>
              <div>万里无云</div>
            </div>
            <div class="detail-item">
              <div>风力2级</div>
              <div>风向正西</div>
            </div>
          </div>
        </div>
        <div class="interesting">
          <div class="interesting-item">无边落木萧萧下</div>
          <div class="interesting-item">不尽长江滚滚来</div>
        </div>
      </div>
      <div class="weather-footer"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App"
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
  // background-image: linear-gradient(to bottom, #6f86d6 0%, #48c6ef 100%);//晚上
  // background-image: linear-gradient(to bottom, #304352 0%, #d7d2cc 100%);//深夜
}
// body 也增加最大最小宽度限制，避免默认100%宽度的 block 元素跟随 body 而过大过小
body {
  max-width: 540px;
  min-width: 320px;
  margin: 0 auto;
  font-size: 0.15rem;
  #app {
    padding: 0.3rem;
    position: relative;
    height: 100vh;
    box-sizing: border-box;
    .switch-dot {
      height: 0.3rem;
      display: flex;
      justify-content: center;
      align-items: center;
      margin-bottom: 0.2rem;
      .dot-item {
        width: 0.08rem;
        height: 0.08rem;
        border-radius: 50%;
        margin: 0 0.05rem;
        background: #fff;
      }
    }
    .weather-body {
      .weather-brief {
        .brief-city {
          font-size: 0.4rem;
        }
        .brief-tempreture {
          font-size: 0.8rem;
        }
        .brief-detail {
          display: flex;
          justify-content: space-between;
          font-size: 0.25rem;
          text-align: center;
          line-height: 0.4rem;
        }
        .brief-item {
          margin-bottom: 0.1rem;
        }
      }
      .interesting {
        box-sizing: border-box;
        position: absolute;
        bottom: 0.3rem;
        left: 0rem;
        right: 0.3rem;
        height: 5.2rem;
        writing-mode: vertical-rl;
        font-size: 0.3rem;
        padding: 0.6rem 0;
        background: url("./assets/guangzhou.png") left bottom no-repeat;
        background-size: 4rem;
        .interesting-item {
          line-height: 0.6rem;
          letter-spacing: 0.12rem;
        }
        .interesting-item:nth-child(even) {
          padding-top: 0.42rem;
        }
      }
    }
  }
}
</style>

