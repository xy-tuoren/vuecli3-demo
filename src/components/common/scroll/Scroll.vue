<template>
    <div class="wrapper" ref="wrapper">
        <div class="content">
            <slot></slot>
        </div>
    </div>
</template>

<script>
    import BScroll from 'better-scroll'
    export default {
        name: "Scroll",
        props: {
          probeType: {
              type:Number,
              default:0
          },
          pullUpLoad: {
              type:Boolean,
              default: false
          }
        },
        data() {
          return {
              scroll:null
          }
        },
        mounted() {
            //创建BScroll对象
            this.scroll = new BScroll(this.$refs.wrapper,{
                click:true,
                prototype: this.prototype,
                pullUpLoad: this.pullUpLoad,
            })
            //监听滚动事件
            this.scroll.on('scroll',(position) => {
                this.$emit('scroll',position)
            })
            //监听上拉事件
            this.scroll.on('pullingUp',() => {
                this.$emit('pullingUp')
            })
        },
        methods: {
            //多少时间回到指定滚动条位置
            scrollTo(x,y,time=300) {
                this.scrollTo(x,y,time)
            },
            //上拉加载更多每次刷新必须调用此方法
            finishPullUp() {
                this.scroll.finishPullUp()
            }
        }
    }
</script>

<style scoped>

</style>