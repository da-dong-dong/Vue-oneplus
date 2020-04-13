<template>
  <div class="banarBox" ref="banarBox">
    <div class="banarImg">
      <div class="banarText" v-show="flag">
        <p class="animated slideInRight">Shot on OnePlus</p>
        <span class="animated slideInLeft">我要参加</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      flag: false
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll, true);
    this.handleScroll();
  },
  methods: {
    // 保存滚动值，这是兼容的写法
    handleScroll() {
      this.scrollTop =
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop;
      if (this.$refs.banarBox.getBoundingClientRect().top <= 400) {
        this.flag = true;
      } else {
        this.flag = false;
      }
    }
  }
};
</script>

<style lang="scss" scoped>
.banarBox {
  width: 100%;
  height: 720px;
  position: relative;
}
.banarImg {
  width: 100%;
  height: 100%;
  background: url(../assets/img/8.jpg) no-repeat center center;
}
.banarText {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  p {
    white-space: nowrap;
    font-size: 48px;
    color: #ffffff;
    transition: all 0.6s ease;
    padding-bottom: 20px;
  }
  span {
    transition: all 0.6s ease;
    display: inline-block;
    margin-left: 5px;
    margin-right: 5px;
    margin-bottom: 10px;
    vertical-align: middle;
    color: #fff;
    border: 2px solid #fff;
    height: 40px;
    padding: 0 20px;
    text-align: center;
    cursor: pointer;
    white-space: nowrap;
    line-height: 40px;
  }
}
// 响应式
@media only screen and (max-width: 767px) {
  .banarBox {
    height: 560px;
  }
  .banarText p {
    font-size: 28px;
  }
}
</style>
