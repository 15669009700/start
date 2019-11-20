<template>
    <div id="tab-bar">
      <!--<slot name="item-icon"></slot>-->
      <!--<slot name="item-text"></slot>-->
      <slot></slot>
      <!--App.vue里面用<tab-bar>使用了这里的位置，把这里的插槽应用在App.vue里面-->
    </div>
</template>

<script>
    export default {
        name: "tabbar"
    }
</script>

<style scoped>
  #tab-bar{
    display: flex;
    /*弹性布局，下面的子元素的浮动，清除浮动和vertical-align属性失效*/
    background-color: #f6f6f6;
    position: fixed;
    /*绝对定位（相对于浏览器）*/
    left: 0;
    right: 0;
    bottom: 0;
    box-shadow: 0 -3px 1px rgba(100,100,100,.1);
    /*box-shadow(向框添加一个或多个阴影)：0(水平的阴影位置) -3px(垂直的阴影位置)
    1px(模糊距离或者阴影尺寸) 后面是颜色和透明度*/
  }
</style>
