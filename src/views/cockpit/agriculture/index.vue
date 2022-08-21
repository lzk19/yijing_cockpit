<template>
  <el-container>
    <Left></Left>
    <el-container>
      <el-header>
        <Header></Header>
      </el-header>
      <el-main>
        <Back></Back>
      </el-main>
      <!--<el-footer>
        <Bottom></Bottom>
      </el-footer>-->
    </el-container>
    <Right></Right>
  </el-container>
</template>

<script>
import Back from '../background/index.vue'
import Header from '../header/index.vue'
import Left from './left/index.vue'
import Right from './right/index.vue'
// import Bottom from '../bottom/agricultureBottom.vue'
export default{
  components:{
    Back,
    Header,
    Left,
    Right

  }
}

</script>

<style lang="scss" scoped>
.el-header {
  height: 16vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.el-footer {
  height: 7.5vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
