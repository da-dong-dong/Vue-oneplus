<template>
  <div class="hello">
    <section>
      <div class="header-Box">
        <transition name="el-zoom-in-bottom">
          <img
            class="header-img animated fadeInUp faster"
            v-show="show2"
            src="../assets/img/1.jpg"
            alt=""
          />
        </transition>
        <div class="header-text">
          <ul>
            <li class="header-text1  animated fadeInUp ">
              永不言弃，追求极致。
            </li>
            <li class="header-speed "></li>
            <li class="header-text2  animated fadeInUp  ">
              欢迎小罗伯特·唐尼，<br />
              加入 OnePlus 大家庭。
            </li>
            <li class="header-speed1"></li>
            <li
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
      headerRigh: false
    };
  },
  mounted() {
    this.show2 = true;
  },
  methods: {
    enter() {
      console.log("111");
      this.headerRigh = true;
    },
    leave() {
      this.headerRigh = false;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header-Box {
  transition: all 0.3s ease;
  height: 300px;
  background-color: #4e6682;
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
}
.header-text {
  position: absolute;
  color: #fff;
  left: 20%;
  right: 52%;
  top: 50%;
  transform: translateY(-50%);
  white-space: nowrap;
}
.header-text1 {
  font-size: 48px;
}
.header-speed {
  height: 40px;
}
.header-text2 {
  font-size: 16px;
  line-height: 1.5;
  font-weight: 400;
}
.header-speed1 {
  height: 10px;
}
.header-speed3 {
  cursor: pointer;
}
.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active for below version 2.1.8 */ {
  transform: translateX(100px);
}

// 响应式
@media only screen and (max-width: 767px) {
  .header-text1 {
    font-size: 28px;
  }
}
</style>
