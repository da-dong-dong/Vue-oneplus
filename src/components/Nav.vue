<template>
  <el-container>
    <el-header class="Nav-hader">
      <el-row :gutter="2">
        <el-col :sm="3"
                :xs="24">
          <div class="grid-content bg-purple">
            <i class="header-logo">logo</i>
          </div>
        </el-col>
        <el-col :sm="18"
                :xs="0"
                class="header-left">
          <div class="grid-content "
               :style="{background:(!flag?'#fff':'none')}">

            <i :class="flag ? 'el-icon-menu' : 'el-icon-close'"
               class="el-cin"
               @click="clickIcon"></i>

            <ul class="header-nav bg-purple-light"
                :class="flag ? 'shouFlag' : ''">
              <li @click="clickIcon1">
                <router-link class="series-slide-trigger"
                             to="/">Home</router-link>
                <transition>
                  <i class="icoffo"
                     :class="flag1 ? 'el-icon-plus' : 'el-icon-minus'"></i>
                </transition>
                <div class="header-nav-box"
                     :class="flag1 ? 'shouFlag' : ''">
                  <ul>
                    <li>
                      <i class="el-icon-share">
                        <p>
                          <router-link to="/">手机</router-link>
                        </p>
                      </i>
                    </li>
                  </ul>
                </div>
              </li>
              <li>
                <router-link class="series-slide-trigger"
                             to="/">Home</router-link>
              </li>
              <li>
                <router-link class="series-slide-trigger"
                             to="/">Home</router-link>
              </li>
              <li>
                <router-link class="series-slide-trigger"
                             to="/">Home</router-link>
              </li>
              <li>
                <router-link class="series-slide-trigger"
                             to="/">Home</router-link>
              </li>
            </ul>

          </div>
        </el-col>
        <el-col :sm="3"
                :xs="0"
                class="header-right">
          <div class="grid-content bg-purple">
            <i class="el-icon-user-solid"></i>
          </div>
        </el-col>
      </el-row>
    </el-header>
  </el-container>
</template>

<script>
export default {
  data () {
    return {
      flag: true,
      flag1: true
    };
  },
  methods: {
    clickIcon () {
      this.flag = !this.flag;
    },
    clickIcon1 () {
      this.flag1 = !this.flag1;
    }
  }
};
</script>

<style lang="scss" scoped>
.Nav-hader {
  position: relative;
  text-align: center;
  background-color: #fff;
}
.header-logo {
  font-size: 40px;
  color: #eb0028;
}
.header-nav {
  li,
  a {
    font-size: 14px;
    display: inline-block;
    vertical-align: top;
    line-height: 60px;
    height: 60px;
    min-width: 60px;
    margin-right: -1px;
    cursor: pointer;
    box-sizing: border-box;
  }
  li {
    &:hover .header-nav-box {
      display: block;
    }
  }
  .series-slide-trigger {
    padding: 0 20px;
    border-bottom: 2px solid transparent;
    color: #000;
    &:hover {
      border-bottom: 2px solid #eb0028;
      color: #000;
    }
  }
}
.header-nav-box {
  position: absolute;
  left: 50%;
  width: 100vw;
  min-height: 160px;
  -webkit-transform: translate(-50%);
  transform: translate(-50%);
  background-color: #fff;
  text-align: center;
  cursor: auto;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  display: none;
  z-index: 100;
  ul {
    margin-top: 30px;
  }
  .el-icon-share {
    font-size: 30px;
    text-align: center;
    padding-top: 10px;
    line-height: 35px;
  }
  li {
    a {
      font-size: 14px;
    }
    &:hover .el-icon-share {
      color: #eb0028;
    }
    &:hover a {
      color: #eb0028;
    }
  }
}
.el-cin {
  display: none;
  color: #333;
  transition: 1s;
}
.icoffo {
  display: none;
  color: #333;
  transition: 1s;
}
.bg-purple {
  height: 60px;
  line-height: 60px;
  font-size: 25px;
  cursor: pointer;
  color: #333;
}

// 响应式
@media only screen and (max-width: 767px) {
  .Nav-hader .grid-content .shouFlag {
    display: none !important;
  }
  .shouFlag {
    display: none;
  }
  .header-right {
    display: block;
    position: absolute;
    right: 40px;
  }
  .header-left {
    display: block;
  }
  .bg-purple-light {
    background: #fff;
    float: 1;
    height: 100%;
    position: fixed;
    top: 60px;
    z-index: 10;
    width: 100%;
  }
  .el-cin {
    display: block;
    font-size: 25px;
    position: absolute;
    top: 20px;
    left: 15px;
  }
  .icoffo {
    display: inline-block;
    position: absolute;
    right: 30px;
    top: 20px;
    font-size: 25px;
  }
  .bg-purple-light li {
    display: block;
    height: auto;
    padding: 0 30px;
  }
  .header-nav .series-slide-trigger {
    border-bottom: 1px solid #333;
    color: #000;
    box-sizing: border-box;
    text-align: left;
    width: 100%;
    font-size: 18px;
  }
  .header-nav > li {
    position: relative;
  }
  .header-nav-box {
    position: relative;
  }
}
</style>
