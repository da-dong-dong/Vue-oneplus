<template>
  <div class="footer2">
    <el-row :gutter="10">
      <el-col :sm='10'
              :xs="24">
        <div class="grid-content bg-purple">
          <i class="el-icon-medal-1"></i>
          <span>中国大陆 ( 简体中文 / CNY )
          </span>
        </div>
      </el-col>
      <el-col :sm='14'
              :xs="24">
        <div class="grid-content bg-purple-light">
          <i class="el-icon-phone"></i>
          <span>400 - 888 - 1111</span>
          <span class="spanbos"></span>
          <i class="el-icon-date"></i>
          <span>400 - 888 - 1111</span>
        </div>
      </el-col>

    </el-row>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.footer2 {
  max-width: 75pc;
  margin: 30px auto;
}
.el-icon-medal-1 {
  font-size: 30px;
  color: red;
  margin: 0 10px 0 20px;
}
.bg-purple-light {
  text-align: right;
  color: #09c;
  i {
    font-size: 30px;
    margin: 0 10px;
  }
}
.spanbos {
  display: none;
}
// 响应式
@media only screen and (max-width: 768px) {
  .bg-purple-light {
    text-align: center;
  }
  .grid-content {
    margin-top: 20px;
  }
}
// 响应式
@media only screen and (max-width: 320px) {
  .spanbos {
    display: block;
  }
}
</style>