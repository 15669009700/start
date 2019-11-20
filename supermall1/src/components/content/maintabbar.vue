<template>
  <tab-bar>
    <!--为什么标签是这样子的<tab-bar>而不是<tabbar>：父子组件通信里面有驼峰标识,props里面需用-连接，否则会报错的-->
    <tab-bar-item link="/home">
      <img slot="item-icon" src="~assets/img/home.png" alt="">
      <img slot="item-icon-active" src="~assets/img/home-active.png" alt="">
      <div slot="item-text">优化</div>
    </tab-bar-item>
    <tab-bar-item link="/category" activeColor="blue">
      <img slot="item-icon" src="~assets/img/category.png" alt="">
      <img slot="item-icon-active" src="~assets/img/category-active.png" alt="">
      <div slot="item-text">分类</div>
    </tab-bar-item>
    <tab-bar-item link="/cart" activeColor="blue">
      <img slot="item-icon" src="~assets/img/cart.png" alt="">
      <img slot="item-icon-active" src="~assets/img/cart-active.png" alt="">
      <div slot="item-text">设置</div>
    </tab-bar-item>
    <tab-bar-item link="/profile" activeColor="blue">
      <img slot="item-icon" src="~assets/img/profile.png" alt="">
      <img slot="item-icon-active" src="~assets/img/profile-active.png" alt="">
      <div slot="item-text">我的</div>
    </tab-bar-item>
  </tab-bar>
</template>

<script>

  import TabBar from 'components/common/TabBar/tabbar'
  import TabBarItem from 'components/common/TabBar/TabBarItem'
    //因为有别名，所以前面的../可以省略
    export default {
        name: "maintabbar",
      components:{
        TabBar,
        TabBarItem
      }
    }
</script>

<style scoped>

</style>
