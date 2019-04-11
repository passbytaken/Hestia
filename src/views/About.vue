<template>
  <div class="about">
    <!-- <h1>This is an about page</h1> -->
    <el-tabs v-model="activeName" @tab-click="handleClick">
    <el-tab-pane label="weibo" name="first">微博</el-tab-pane>
    <el-tab-pane label="油管" name="second">YouTube</el-tab-pane>
    <el-tab-pane label="哔哩哔哩" name="third">B站</el-tab-pane>
    <el-tab-pane label="webpage" name="fourth" id="card">
      <el-card class="box-card" shadow="hover">
        <div class="box-card">
          <div v-for="o in 4" :key="o" class="text item">
            {{'列表内容 ' + o }}
          </div>
        </div>
      </el-card>
    </el-tab-pane>
  </el-tabs>
  </div>
</template>

<script>
export default {
  data () {
    return {
      activeName: 'first'
    };
  },
  methods: {
    handleClick(tab, event) {
      console.log(tab, event)
      console.log(1)
    }
  }
}
</script>

<style>
  .text {
    font-size: 14px;
  }

  .item {
    padding: 18px 0;
  }

  .box-card {
    width: 480px;
    height: 240px;
  }
  #card {
    margin: 30px
  }
</style>