<template>
  <div class="ThrenChild"
       ref="ThrenChild">
    <div class="TrenImg">
      <img v-show="flag"
           class="animated tada"
           :src="this.datas.image"
           alt="" />
    </div>
    <div class="TranText">
      <h4>{{ this.datas.test1 }}</h4>
      <p>{{ this.datas.test2 }}</p>
      <span>了解更多</span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["datas"],
  data () {
    return {
      flag: false
    };
  },
  mounted () {
    this.flag = true;
    window.addEventListener("scroll", this.handleScroll, true);
    this.handleScroll();
  },
  methods: {
    // 保存滚动值，这是兼容的写法
    handleScroll () {
      this.scrollTop =
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop;
      if (this.$refs.ThrenChild.getBoundingClientRect().top <= 500) {
        this.flag = true;
      } else {
        this.flag = false;
      }
    }
  }
};
</script>

<style lang="scss" scoped>
.ThrenChild {
  width: 100%;
  height: 100%;
  transition: all 0.5s ease;

  &:hover {
    box-shadow: 1px 1px 10px #666;
  }
  overflow: hidden;
}
.TrenImg {
  transition: all 0.5s ease;

  &:hover {
    transform: scale(1.07);
  }
  img {
    width: 100%;
  }
}
.TranText {
  background: #fff;
  padding: 20px;
  h4 {
    height: 24px;
    font-size: 1pc;
    font-weight: 400;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.5;
    letter-spacing: normal;
    color: #666;
    margin: 0;
  }
  p {
    font-size: 18px;
    font-weight: 400;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.5;
    letter-spacing: normal;
    color: #000;
    margin-top: 10px;
  }
  span {
    line-height: 1.5;
    margin-top: 30px;
    color: #000;
    text-decoration: none;
    display: block;
    color: #09c;
  }
}
</style>
