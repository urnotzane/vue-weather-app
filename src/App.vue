<template>
  <div id="app">
    <div class="switch-dot"></div>
    <div class="switch-body">
      <div class="weather-header"></div>
      <div class="weather-body">
        <div class="weather-brief">
          <div class="brief-city">
            深圳
          </div>
          <div class="brief-tempreture">
            <span>22°C</span>
            <span>晴</span>
          </div>
          <div class="brief-detail">
            <div class="detail-item">
              <div>巳时</div>
              <div>日出三竿</div>
            </div>
            <div class="detail-item">
              <div>万里无云</div>
              <div>15°~24°</div>
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

<style lang="less">
html {
  font-size: 16px;
  body {
    margin: 0;
  }
}
</style>

