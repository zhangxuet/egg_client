<template>
  <div id="app">
    <van-tabbar route>
      <van-tabbar-item replace to="/" icon="home-o">
        首页
      </van-tabbar-item>
      <van-tabbar-item replace to="/add" icon="plus">
        发布
      </van-tabbar-item>
    </van-tabbar>
    <router-view/>
  </div>
</template>

<script>
import { Button, Tabbar, TabbarItem } from 'vant'
export default {
  name: 'Home',
  components: {
    [Button.name]: Button,
    [Tabbar.name]: Tabbar,
    [TabbarItem.name]: TabbarItem
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #333;
}
</style>
