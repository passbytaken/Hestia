<template>
  <div class="nav">
      <el-row>
          <el-col :span="24"><div class="grid-content bg-purple-dark"><Swiper></Swiper></div></el-col>
      </el-row>

      <el-row>
        <el-col :span="12"><div class="grid-content bg-purple"></div></el-col>
        <el-col :span="12"><div class="grid-content bg-purple-light"></div></el-col>
      </el-row>
  </div>
  
</template>

<script>
import axios from 'axios'
import { error } from 'util';
import Swiper from '@/components/Swiper.vue'

export default {
  
  components: {
    Swiper
  },
  data () {},

  mounted () {},

}
</script>
<style>
.fav {
  background-color: black;
  width: 60%;
  margin: 0 auto;
  border:1px solid #B3BFB8;
  border-radius: 15px;
}
h1 {
  color: white;
  
}
.currency {
  color: #B3BFB8
}
</style>

