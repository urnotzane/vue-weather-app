<template>
  <div class="home">
    
    <div class="nav-bar">
      <div @click="bindMenu" class="iconfont icon-liebiao"></div>
      <div class="switch-dot">
        <span class="dot-item"></span>
        <span class="dot-item"></span>
        <span class="dot-item"></span>
      </div>
      <div class="iconfont icon-shezhi"></div>
    </div>
    <div class="switch-body">
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
import Menu from "./Menu";
export default {
  name: "App",
  components: {
    Menu
  },
  data() {
    return {};
  },
  methods: {
    bindMenu: function(e) {
      this.$router.push({ path: "/Menu" });
    }
  }
};
</script>

<style lang="scss" scoped>
.home{
  width: 100%;
  height: 100%;
}
.nav-bar {
  width: 100%;
  height: 0.666rem;
  line-height: 0.666rem;
  display: flex;
  justify-content: space-between;
  padding: 0 0.3rem;
  box-sizing: border-box;

  .switch-dot {
    height: 0.666rem;
    line-height: 0.666rem;
    display: flex;
    justify-content: center;
    align-items: center;
    .dot-item {
      width: 0.08rem;
      height: 0.08rem;
      border-radius: 50%;
      margin: 0 0.05rem;
      background: #fff;
    }
  }
}
.weather-body {
  padding: 0 0.3rem;
  .weather-brief {
    .brief-city {
      font-size: 0.35rem;
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
    background: url("../assets/guangzhou.png") left bottom no-repeat;
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
</style>

