<template>
  <div class="RowBox">
    <el-row :gutter="10">
      <el-col :sm="12">
        <div class="grid-content bg-purple">
          <BoxChild :datas='datas[0]' />
        </div>
      </el-col>
      <el-col :sm="12">
        <div class="grid-content bg-purple-light">
          <BoxChild :datas='datas[1]' />
        </div>
      </el-col>
      <el-col :sm="12">
        <div class="grid-content bg-purple">
          <BoxChild :datas='datas[2]'
                    :color='"#fff"' />
        </div>
      </el-col>
      <el-col :sm="12">
        <div class="grid-content bg-purple-light">
          <BoxChild :datas='datas[3]' />
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import BoxChild from "./BoxChild";
import img4 from "@/assets/img/4.jpg";
import img5 from "@/assets/img/5.jpg";
import img6 from "@/assets/img/6.jpg";
import img7 from "@/assets/img/7.jpg";
export default {
  data () {
    return {
      datas: [
        { text1: "以旧换新 ", text2: "最高额外补贴1100元", image: img4 },
        { text1: "OnePlus 2020 春季校园招聘 ", text2: "线上全面开启", image: img5 },
        { text1: "教育用户认证享优惠 ", text2: "了解更多", image: img6 },
        { text1: "零售店体验与购买 ", text2: "了解更多", image: img7 },
      ]
    };
  },
  components: {
    BoxChild
  }
};
</script>

<style lang="scss" scoped>
.RowBox {
  margin: 20px 0;
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
  margin-bottom: 20px;
}
</style>
