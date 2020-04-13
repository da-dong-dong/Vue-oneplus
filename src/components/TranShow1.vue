<template>
  <div class="hello" ref="hello1">
    <section>
      <div class="header-Box">
        <transition name="el-zoom-in-bottom">
          <div
            class="header-img animated fadeInUp faster"
            v-show="show2"
            src="../assets/img/3.jpg"
            alt=""
          />
        </transition>
        <div class="header-text">
          <ul>
            <li v-show="show2" class="header-text0 animated fadeInUp">
              全系 90Hz，流畅新标杆
            </li>

            <li v-show="show2" class="header-text1  animated fadeInUp ">
              OnePlus 7T
            </li>
            <li class="header-speed "></li>
            <li v-show="show2" class="header-text2  animated fadeInUp  fast">
              ￥2999 起
            </li>
            <li class="header-speed1"></li>
            <li v-show="show2" class="header-speed3 animated fadeInUp 		">
              <span class="header-span"> 立即预约</span>
            </li>
            <li
              v-show="show2"
              class="header-speed3 animated fadeInUp 	"
              @mouseenter="enter()"
              @mouseleave="leave()"
            >
              <span>前往了解一下</span>
              <transition name="slide-fade">
                <i v-show="headerRigh" class="el-icon-arrow-right"></i>
              </transition>
            </li>
          </ul>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      show2: false,
      headerRigh: false,
      // 滚动条的高度
      scrollTop: 0,
      //元素到达顶部距离
      elTop: 0
    };
  },
  mounted() {
    //this.show2 = true;
    window.addEventListener("scroll", this.handleScroll, true);
    this.handleScroll();
  },
  destroyed() {
    window.removeEventListener("scroll", this.scroll); //注销监听页面滚动事件
  },
  methods: {
    enter() {
      console.log("111");
      this.headerRigh = true;
    },
    leave() {
      this.headerRigh = false;
    },
    // 保存滚动值，这是兼容的写法
    handleScroll() {
      this.scrollTop =
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop;
      //console.log(this.scrollTop);
      if (this.$refs.hello1.getBoundingClientRect().top <= 400) {
        this.show2 = true;
      } else {
        this.show2 = false;
      }
    },

    // 滚动条回到顶部
    backTop() {
      if (this.scrollTop > 10) {
        document.documentElement.scrollTop = 0;
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header-Box {
  transition: all 0.3s ease;
  height: 680px;
  //background-color: #4e6682;
  position: relative;
  overflow: hidden;
  //background: 50% no-repeat;
}
.header-img {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  background: url(../assets/img/3.jpg) no-repeat center center;
  background-size: cover;
}
.header-text {
  position: absolute;
  color: #000;
  left: 20%;
  right: 52%;
  top: 50%;
  transform: translateY(-50%);
  white-space: nowrap;
}
.header-text1 {
  font-size: 48px;
  animation-delay: 0.5s;
}
.header-speed {
  height: 40px;
}
.header-text2 {
  font-size: 24px;
  line-height: 1.5;
  font-weight: 400;
  animation-delay: 0.6s;
}
.header-text0 {
  animation-delay: 0.4s;
}
.header-speed1 {
  height: 10px;
}
.header-speed3 {
  cursor: pointer;
  animation-delay: 0.7s;
}
.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active for below version 2.1.8 */ {
  transform: translateX(100px);
}
.header-span {
  height: 40px;
  padding: 0 20px;
  border-radius: 4px;
  display: inline-block;
  text-align: center;
  border: 1px solid #000;
  color: #000;
  line-height: 40px;
  margin-bottom: 20px;
}
// 响应式
@media only screen and (max-width: 767px) {
  .header-text1 {
    font-size: 28px;
  }
  .header-text {
    top: 20%;
    width: 100%;
    padding: 10%;
    left: -10%;
    text-align: center;
  }
  .header-img {
    background: url(../assets/img/3.1.jpg) no-repeat center center;
    background-size: cover;
  }
}
</style>
