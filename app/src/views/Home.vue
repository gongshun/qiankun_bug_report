<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" >
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <el-select v-model="value" placeholder="请选择">
          <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value">
          </el-option>
        </el-select>
    <el-button @click="drawer = true" type="primary">
      点我打开drawer
    </el-button>
    <el-drawer
      title="我是标题"
      :visible.sync="drawer"
      direction="rtl"
    >
        <el-select v-model="value1" placeholder="请选择">
          <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value">
          </el-option>
        </el-select>
    </el-drawer>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  data() {
    return {
      drawer: false,
      options: [{
        value: '选项1',
        label: '黄金糕'
      }, {
        value: '选项2',
        label: '双皮奶'
      }, {
        value: '选项3',
        label: '蚵仔煎'
      }, {
        value: '选项4',
        label: '龙须面'
      }, {
        value: '选项5',
        label: '北京烤鸭'
      }],
      value: '',
      value1: '',
    }
  }
}
</script>

<style>
#appHash{
  background: #ccc;
}
</style>