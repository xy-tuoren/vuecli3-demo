<template>
  <div id="home">
    <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
  </div>
</template>

<script>
  import NavBar from "components/common/navbar/NavBar";
  import { getHomeMultidate } from "network/home";

  export default {
    name: "Home",
    components: {
      NavBar
    },
    data() {
      return {
        result: null
      }
    },
    created() {
      //1.请求多个数据
      getHomeMultidate().then(res => {
        this.result = res;
        console.log(res);
      })
    }
  }
</script>

<style scoped>
  .home-nav {
    background-color: var(--color-tint);
    color: #ffffff;
  }
</style>
