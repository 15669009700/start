<template>

    <!--<img name="item-icon" src="../../assets/img/home.png"/>-->
    <!--<div name="item-text">首页</div>-->
    <div class="tab-bar-item" @click="itemClick">
      <div v-if="!isActive"><slot name="item-icon"></slot></div>
      <div v-else><slot name="item-icon-active"></slot></div>
      <div :style="activeStyle"><slot name="item-text"></slot></div>
      <!--:style这里的属性名称s还小写，注意！-->
<!--:class="{active:isActive}" 注意这里需要一个大{}来保住一个动态的active，赋值给active的布尔值需：冒号-->
      <!--App.vue里面写内容，动态的绑定在这个插槽中-->
      <!--<img src="../../assets/img/home.png" alt="">-->
      <!--<div>首页</div>-->
    </div>

</template>

<script>
    export default {
        name: "TabBarItem",
      props:{
        link:String,
        activeColor:{
          type:String,
          default:'skyblue'
        }

      },
      computed:{
          isActive(){
            return this.$route.path.indexOf(this.link) !==-1

          //  点击切换页面
          },
        activeStyle(){
            return this.isActive ? {color: this.activeColor}: {}
        }
      },
      methods:{
        itemClick(){
          // console.log('itemClick');
          if(this.$route.path!==this.link){this.$router.replace(this.link)}
        //这里太多path 其中一个是活跃的path页面，一个是被点击的标签里面的link属性值,微笑，终于分得清哪个是path哪个是link
        }
      },

    }

</script>

<style scoped>
  .tab-bar-item{
    flex: 1;
    /*均匀宽*/
    text-align: center;
    /*居中显示*/
    height: 49px;
    /*常用高度49px，下面按钮的高度*/
    font-size: 14px;
    margin-top: 2px;
    vertical-align: middle;
    /*消除图片下面的3px空白*/
  }
  .tab-bar-item img{
    width: 24px;
    height: 24px;
  }
</style>
