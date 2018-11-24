<template>
  <div class="menu-content">
    <div class="nav-bar">
      <div @click="bindBack" class="iconfont icon-back"></div>
      <div>城市列表</div>
      <div class="iconfont icon-bianji"></div>
    </div>
    <div class="city-list">
      <div class="list-cell" v-for="item in CityList" :key="item.id">
        <div class="name">{{item.name}}</div>
        <div class="tempreture">{{item.tempreture}}°C</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Menu",
  data() {
    return {
      CityList: [
        {
          id: 1,
          name: "深圳",
          tempreture: "25"
        },
        {
          id: 2,
          name: "广州",
          tempreture: "23"
        },
        {
          id: 3,
          name: "哈尔滨",
          tempreture: "-10"
        }
      ]
    };
  },
  methods: {
    bindBack: function() {
      this.$router.back();
    }
  }
};
</script>

<style lang="scss" scoped>
.menu-content {
  .nav-bar {
    width: 100%;
    height: 0.666rem;
    line-height: 0.666rem;
    display: flex;
    justify-content: space-between;
    padding: 0 0.3rem;
    box-sizing: border-box;
  }
  .city-list {
    .list-cell {
      display: flex;
      justify-content: space-between;
      font-size: 0.3rem;
      padding: 0 0.3rem;
      height: 0.8rem;
      line-height: 0.8rem;
    }
    .list-cell:nth-child(odd) {
      background: rgba(255, 255, 255, 0.1);
    }
  }
}
</style>

