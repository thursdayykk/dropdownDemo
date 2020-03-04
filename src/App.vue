<template>
  <div id="app">
   <el-container>
      <el-header>
        <!-- 下拉框 -->
        <DropDown :data="menu" @cur-hover="curHover"/>
      </el-header>
      <el-container>
        <el-aside width="200px">Aside</el-aside>
        <el-main>
          <!-- 内容区 -->
          <!-- 下拉框的菜单 -->
          <DropDownItem :menu="dropdownItem" :cur="curItemIndex" @mouse-leave="leave"/>
          <!-- 路由 -->
          <router-view />
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
import DropDown from "@/components/dropdown"
import DropDownItem from "@/components/dropdown/item"
export default {
  name: 'App',
  components:{DropDown,DropDownItem},
  data(){
    return {
      menu:['下拉框1','下拉框2','下拉框3','下拉框4','下拉框5'],
      dropdownItem:[
        ['下拉框1','下拉框1','下拉框1','下拉框1','下拉框1','下拉框1'],
        ['下拉框2','下拉框2','下拉框2','下拉框2','下拉框2',],
        ['下拉框3','下拉框3','下拉框3','下拉框3']
      ],
      curItemIndex:-1 // 初始化-1 不显示
    }
    
  },
  methods:{
    curHover(index){
      // console.log(index)
      this.curItemIndex = index
    },
    leave(){
      this.curItemIndex = -1
    }
  }
}
</script>

<style>
.el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  
  .el-aside {
    background-color: #D3DCE6;
    color: #333;
    text-align: center;
    height:100%;
  }
  
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
    padding:0px;
    position:relative;
  }
  .el-container {
    height:100%;
  }
  body > .el-container {
    /* margin-bottom: 40px; */
    
  }
body,html{
  margin:0;
  height:100%;
}
#app {
  height:100%;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>
