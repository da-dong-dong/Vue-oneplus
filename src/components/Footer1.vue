<template>
  <div class="footerBox">
    <div class="footerTop">
      <el-row :gutter="10"
              class="footerTopFlex">
        <el-col :xs='12'
                :sm='6'>
          <div class="footerTopBox">
            <i class="el-icon-eleme"></i>
            <span>7天无理由退货</span>
          </div>

        </el-col>
        <el-col :xs='12'
                :sm='6'>
          <div class="footerTopBox">
            <i class="el-icon-eleme"></i>
            <span>7天无理由退货</span>
          </div>
        </el-col>
        <el-col :xs='12'
                :sm='6'>
          <div class="footerTopBox">
            <i class="el-icon-eleme"></i>
            <span>7天无理由退货</span>
          </div>
        </el-col>
        <el-col :xs='12'
                :sm='6'>
          <div class="footerTopBox">
            <i class="el-icon-eleme"></i>
            <span>7天无理由退货</span>
          </div>
        </el-col>
      </el-row>

    </div>
  </div>

</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.footerBox {
  width: 100%;
  border-bottom: 1px solid rgba(0, 0, 0, 0.2);
}
.footerTop {
  display: -webkit-box;
  display: flex;
  -webkit-box-pack: start;
  justify-content: flex-start;
  flex-wrap: wrap;
  max-width: 75pc;
  margin: auto;
}
.footerTopBox {
  height: 137px;
  text-align: center;
  width: 100%;
  i {
    display: block;
    font-size: 35px;
    line-height: 83px;
    cursor: pointer;
  }
}
.footerTopFlex {
  width: 100%;
}
</style>