<template>
  <div>
    <el-container>
      <el-header style="margin-top: -80px">
        <!--<el-link @click="userlogin()" style="margin-left: 905px;height: 30px">登陆</el-link>-->
        <!--<el-link @click="userregist()" style="margin-left: 50px;height: 30px">注册</el-link>-->
      </el-header>
    </el-container>
    <el-header>
      <img src="../assets/index/logo.gif" height="60px" style="float: left;margin-left: 300px">
      <el-link @click="backindex()" style="float: left;margin-left: 0px"><img src="../assets/index/newlogo.png" height="60px" style="float: left;margin-left: 0px"></el-link>
      <el-input type="text" v-model="searchinput" style="width: 350px;float: left;margin-left: 40px"></el-input>
      <el-button style="width: 120px;text-align: center;margin-left: -462px" @click="search()">全网搜索</el-button>
      <el-link @click="ask()" type="primary" style="height: 30px;">向医生提问</el-link>
    </el-header>
    </div>
</template>

<script>
  import ElInput from "../../node_modules/element-ui/packages/input/src/input";
  import ElLink from "../../node_modules/element-ui/packages/link/src/main";
  import ElContainer from "../../node_modules/element-ui/packages/container/src/main";
  import ElButton from "../../node_modules/element-ui/packages/button/src/button";
  export default {
    components: {
      ElButton,
      ElContainer,
      ElLink,
      ElInput
    },
    name: 'headerno',
    data () {
      return {
        searchinput: '',
      }
    },
    methods: {
      search: function () {
        if (this.searchinput == '') {
          alert('请输入搜索关键字')
        } else {
          var road = 'https://www.baidu.com/s?ie=utf-8&si=muzhi.baidu.com&ct=2097152&wd=' + this.searchinput
          window.location.href = road;
        }
      },
      backindex:function () {
        this.$router.push({path:"/index/main"})
      }
    }
  }
</script>
<style>
  .el-header, .el-footer {
    /*background-color: #B3C0D1;*/
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  body > .el-container {
    margin-bottom: 40px;
  }

  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }

  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
</style>
