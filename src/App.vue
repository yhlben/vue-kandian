<template>
  <div id="app">
    <div class="content">
      <router-view></router-view>
    </div>
    <van-tabbar v-model="active" @change="changeTab">
      <van-tabbar-item icon="home">首页</van-tabbar-item>
      <van-tabbar-item icon="contact">我的</van-tabbar-item>
    </van-tabbar>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      active: 0
    };
  },
  methods: {
    changeTab(active) {
      switch (active) {
        case 0:
          this.$router.push("/home");
          break;
        case 1:
          this.$router.push("/my");
          break;
      }
    }
  }
};
</script>

<style>

/* 修改有赞默认样式 */
.van-card {
  background-color: white;
}
.router-link-active {
  color: #38f !important;
}
.van-tabbar-item__text > a {
  color: black;
}
.van-tab--active {
  color: #38f !important;
}
.van-tabs__nav-bar {
  background-color: #38f !important;
}
.van-button--bottom-action {
  background-color: #38f !important;
}
</style>
