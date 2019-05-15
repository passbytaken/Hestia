<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <WaterMark></WaterMark>
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
