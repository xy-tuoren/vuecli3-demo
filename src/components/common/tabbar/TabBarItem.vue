<template>
  <div class="tab-bar-item" @click="itemClick">
    <div v-if="!isActive"><slot name="item-icon"></slot></div>
    <div v-else><slot name="item-icon-active"></slot></div>
    <div :style="activeColorStyle"><slot name="item-text"></slot></div>
  </div>
</template>

<script>
    export default {
        name: "TabBarItem",
        props: {
            path:String,
            activeColor:{
                type:String,
                default:'red'
            }
        },
        data() {
            return {
                // isActive: true
            }
        },
        computed: {
          isActive() {
              // console.log(this.$route);
              // console.log(this.$router);
              return this.$route.path.indexOf(this.path) !==-1
          },
          activeColorStyle() {
              return this.isActive ? {color:this.activeColor}:{}
          }
        },
        methods: {
            itemClick() {
                this.$router.push(this.path)
            }
        }
    }
</script>

<style scoped>
  .tab-bar-item {
    flex: 1;
    text-align: center;
    height: 49px;
  }
  .tab-bar-item img {
    width: 18px;
    height: 18px;
    vertical-align: middle;
  }
  .tab-bar-item p {
    font-size: 14px;
    height: 18px;
  }
</style>
