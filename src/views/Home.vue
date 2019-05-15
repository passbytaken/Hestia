<template>
  <div class="home">
    <WaterMark></WaterMark>
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
    
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import WaterMark from '@/components/WaterMark.vue'
export default {
  name: "home",
  components: { 
    HelloWorld,
    WaterMark
  }
};
</script>
