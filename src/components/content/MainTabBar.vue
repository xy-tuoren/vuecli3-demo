<template>
  <tab-bar>
    <tab-bar-item path="/home" activeColor="pink">
      <img slot="item-icon" src="~assets/img/tabbar/list.svg">
      <img slot="item-icon-active" src="~assets/img/tabbar/listClick.svg">
      <p slot="item-text">首页</p>
    </tab-bar-item>
    <tab-bar-item path="/cart" activeColor="pink">
      <img slot="item-icon" src="~assets/img/tabbar/list.svg">
      <img slot="item-icon-active" src="~assets/img/tabbar/listClick.svg">
      <p slot="item-text">购物车</p>
    </tab-bar-item>
    <tab-bar-item path="/category" activeColor="pink">
      <img slot="item-icon" src="~assets/img/tabbar/list.svg">
      <img slot="item-icon-active" src="~assets/img/tabbar/listClick.svg">
      <p slot="item-text">分类</p>
    </tab-bar-item>
    <tab-bar-item path="/profile" activeColor="blue">
      <img slot="item-icon" src="~assets/img/tabbar/list.svg">
      <img slot="item-icon-active" src="~assets/img/tabbar/listClick.svg">
      <p slot="item-text">用户</p>
    </tab-bar-item>
  </tab-bar>
</template>

<script>
    import TabBar from "../common/tabbar/TabBar";
    import TabBarItem from "../common/tabbar/TabBarItem";
    export default {
        name: "MainTabBar",
        components: {
            TabBar,
            TabBarItem
        }
    }
</script>

<style scoped>

</style>
