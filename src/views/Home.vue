<template>
  <div class="home"
       ref="home">
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <TranShow />
    <TranShow1 />
    <Box />
    <Banar />
    <ThrenBox />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import TranShow from "@/components/TranShow.vue";
import TranShow1 from "@/components/TranShow1.vue";
import Box from "@/components/Box.vue";
import Banar from "@/components/Banar.vue";
import ThrenBox from "@/components/ThrenBox.vue";
import Footer from '@/components/Footer.vue'
export default {
  name: "Home",
  data () {
    return {
      flag: false
    };
  },

  components: {
    HelloWorld,
    TranShow,
    TranShow1,
    Box,
    Banar,
    ThrenBox,
    Footer
  }
};
</script>
<style>
.transition-box {
  margin-bottom: 10px;
  width: 200px;
  height: 100px;
  border-radius: 4px;
  background-color: #409eff;
  text-align: center;
  color: #fff;
  padding: 40px 20px;
  box-sizing: border-box;
  margin-right: 20px;
}
</style>
