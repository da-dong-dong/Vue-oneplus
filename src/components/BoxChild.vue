<template>
  <div class="content"
       ref="content">
    <div class="contentImg ">
      <div v-show="flag"
           class="contentImg animated rubberBand"
           :style="bgImg"></div>
      <div class="contentImgZ"></div>
    </div>
    <div class="contentText"
         :style="{ color: this.color ? this.color : '' }">
      <div v-show="flag"
           class="contentText1 animated flip">
        {{ this.datas.text1 }}
      </div>
      <div v-show="flag"
           class="contentText2 animated fadeInUp">
        {{ this.datas.text2 }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["datas", "color"],
  data () {
    return {
      flag: false,
      bgImg: {
        background: `url(${this.datas.image}) no-repeat center center`
      }
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
      this.scrollTop = document.documentElement.scrollTop;

      if (this.$refs.content.getBoundingClientRect().top <= 400) {
        this.flag = true;
      } else {
        this.flag = false;
      }
    }
  }
};
</script>

<style lang="scss" scoped>
.content {
  width: 100%;
  height: 500px;
  position: relative;
  overflow: hidden;
  text-align: center;
  &:hover .contentImgZ {
    opacity: 1;
  }
}
.contentImg {
  width: 100%;
  height: 100%;

  transition: all 0.5s ease;

  &:hover {
    transform: scale(1.07);
  }
}
.contentImgZ {
  position: absolute;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.3);
  left: 0;
  top: 0;
  transition: all 0.5s ease;
  opacity: 0;
}
.contentText {
  position: absolute;
  left: 50%;
  top: 30px;
  transform: translateX(-50%);
  color: #000000;
}
.contentText1 {
  margin-bottom: 10px;
  font-weight: 400;
  font-size: 30px;
}
.contentText2 {
  margin-bottom: 10px;
  font-weight: 400;

  font-size: 20px;
}
</style>
