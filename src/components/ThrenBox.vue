<template>
  <div class="ThrenBox">
    <el-row :gutter="10">
      <el-col :md="8"
        ><div class="grid-content bg-purple">
          <ThrenChild :datas="this.datas[0]" /></div
      ></el-col>
      <el-col :md="8"
        ><div class="grid-content bg-purple-light">
          <ThrenChild :datas="this.datas[1]" /></div
      ></el-col>
      <el-col :md="8"
        ><div class="grid-content bg-purple">
          <ThrenChild :datas="this.datas[2]" /></div
      ></el-col>
    </el-row>
  </div>
</template>

<script>
import ThrenChild from "./ThrenChild";
import image1 from "../assets/img/9.jpg";
import image2 from "../assets/img/10.jpg";
import image3 from "../assets/img/11.jpg";
export default {
  data() {
    return {
      datas: [
        {
          test1: "媒体",
          test2: "OnePlus 7T 系列获全球多家媒体好评",
          image: image1
        },
        {
          test1: "故事",
          test2: "「美无边界 动则有灵」OnePlus 壁纸背后的故事",
          image: image2
        },
        {
          test1: "报告",
          test2: "「旦用难回」OnePlus 90Hz 实验报告首发",
          image: image3
        }
      ]
    };
  },
  components: {
    ThrenChild
  }
};
</script>

<style lang="scss" scoped>
.ThrenBox {
  width: 1300px;
  margin: 10px auto;
}
.el-col {
  border-radius: 4px;
}
.bg-purple-dark {
  background: #99a9bf;
}
.bg-purple {
  background: #d3dce6;
}
.bg-purple-light {
  background: #e5e9f2;
}
.grid-content {
  border-radius: 4px;
  min-height: 36px;
}
// 响应式
@media only screen and (max-width: 1024px) {
  .ThrenBox {
    width: 100%;
  }
}
</style>
