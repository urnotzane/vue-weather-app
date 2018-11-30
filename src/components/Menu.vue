<template>
  <div class="menu-content">
    <div class="nav-bar">
      <div @click="bindBack" class="iconfont icon-back"></div>
      <div>城市列表</div>
      <div class="iconfont icon-bianji" @click="bindEdit"></div>
    </div>
    <div class="city-list">
      <div class="list-cell" v-for="item in CityList" :key="item.id">
        <div class="name">
          <span class="iconfont icon-back" v-show="inEdit" @click="bindDelete"></span>
          {{item.name}}
        </div>
        <div class="tempreture">
          {{item.tempreture}}°C
          <span class="iconfont icon-liebiao" v-show="inEdit"></span>
        </div>
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
      ],
      inEdit: false //编辑状态
    };
  },
  methods: {
    bindBack() {
      this.$router.back();
    },
    bindEdit() {
      this.inEdit = !this.inEdit;
    },
    bindDelete() {}
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
      // font-size: 0.3rem;
      padding: 0 0.3rem;
      height: 0.6rem;
      line-height: 0.6rem;
      .iconfont {
        font-size: 0.2rem;
        padding: 0.1rem;
      }
    }
    .list-cell:nth-child(odd) {
      background: rgba(255, 255, 255, 0.1);
    }
  }
}
</style>

