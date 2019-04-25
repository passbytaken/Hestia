<template>
  <div class="about">
    <h1>This is an about page</h1>
  <el-tabs v-model="activeName" @tab-click="handleClick">
    <el-tab-pane label="weibo" name="first">微博</el-tab-pane>
    <el-tab-pane label="Youtube" name="fourth" id="card">

      <el-row v-for="(page, index) of pages" :key="index">
        <el-col :span="2" v-for="(item, i) of page" :key="i" :offset="i > 0 ? 2:1">
          <el-card  class="box-card" shadow="hover">
            <div slot="header" class="clearfix">
              <span>{{item.name}}</span>
              <el-button style="float: right; padding: 3px 0" type="text">查看</el-button>
            </div>
            <div v-for="o in item" :key="o.id" class="text item">
              {{o}}
            </div>      
      </el-card>
        </el-col>
      </el-row>
         
    </el-tab-pane>
  </el-tabs>
  </div>
</template>

<script>
export default {
  data () {
    return {
      activeName: 'first',
      allCards:[
        {id:1,name:'微博',url:'http://weibo.com',cotent:'1'},
        {id:2,name:'油管',url:'https://youtube.com',cotent:'2'},
        {id:3,name:'B站',url:'https://bilibili.com',cotent:'3'},
        {id:4,name:'知乎',url:'https://zhihu.com',cotent:'4'},
        {id:5,name:'推特',url:'https://twitter.com',cotent:'5'},
        {id:6,name:'Github',url:'https://github.com',cotent:'6'},
        {id:7,name:'微信',url:'https://wechat.com',cotent:'7'}
        ]
    };
  },
  methods: {
    handleClick(tab, event) {
       //console.log(tab, event)
      console.log(1)
    }
  },
  computed: {
    pages () {
      const pages = []
      this.allCards.forEach((item, index) => {
        const page = Math.floor(index / 2)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
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
    width: 400px;
    height: 250px;
  }
  #card {
    margin: 50px
  }
  .el-col {
    margin-bottom:40px;
    margin-right: 300px
  }
  
  
</style>