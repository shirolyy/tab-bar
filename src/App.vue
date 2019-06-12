<template>
  <div class="app">
    <router-view></router-view>
    <div class="tab-bar">
      <div class="tab-item" @click="toPath('/')" :class="this.$route.path === '/' ? 'active' : ''">
        <i class="el-icon-s-home" style="whidth:100%"></i><br>
        <span>首页</span>
      </div>
      <div class="tab-item" @click="toPath('/goodlist')" :class="this.$route.path === '/goodlist' ? 'active' : ''">
        <i class="el-icon-s-fold"></i>
        <span>列表</span>
      </div>
      <div class="tab-item" @click="toPath('/car')" :class="this.$route.path === '/car' ? 'active' : ''">
        <i class="el-icon-shopping-cart-1"></i>
        <span>购物车</span>
      </div>
      <div class="tab-item" @click="toPath('/user')" :class="this.$route.path === '/user' ? 'active' : ''">
        <i class="el-icon-user-solid"></i>
        <span>我的</span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'app',
  methods:{
    toPath(path){
      this.$router.replace(path)
      console.log(this.$router);
      console.log(this.$route)
    }
  }
}
</script>
<style scoped lang="css">
  *{
    margin: 0;
    padding: 0;
  }
  .tab-bar{
    width: 100%;
    height: 50px;
    bottom: 0;
    margin: 0;
    margin-left: -10px;
    display: flex;
    position: fixed;
    border: 1px solid cadetblue;
  }
  .tab-item{
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
  }  
  .tab-item span{
    margin-top: 30px;
    margin-left: -25px;
  }
  .active{
    color: red;
  }
  </style>