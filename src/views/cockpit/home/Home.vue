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
    </el-container>
    <Right></Right>
  </el-container>
</template>

<script>
import Back from '../background/index.vue'
import Header from "../header/index.vue"
import Left from './left/index.vue'
import Right from './right/index.vue'
export default{
  components:{
    Back,
    Header,
    Left,
    Right,
  }
}

</script>
