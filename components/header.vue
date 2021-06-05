<template>
  <header class="header clearfix">
    <div class="logo">
      <a href="/">
        <img src="~assets/images/mobile-logo.png" class="logo-img" alt="" />
      </a>
    </div>
    <div
      :class="`header_nav ${isOpen ? 'close' : ''}`"
      @click="isOpen = !isOpen"
    ></div>

    <section class="nav_con" :style="{ display: isOpen ? 'block' : 'none' }">
      <div class="nav">
        <ul class="clearfix">
          <li v-for="menu in menuList" :key="menu.code">
            <a :href="menu.url">{{ menu.title }}</a>
          </li>
        </ul>
        <div class="tel">团建顾问：18072966360 胡瑞</div>
      </div>
    </section>
  </header>
</template>
<script>
export default {
  data() {
    return {
      isOpen: false,
      menuList: [
        { title: '首页', code: 'index', url: '/' },
        { title: '旅行团建', code: 'lxtuanjian', url: '/lxtuanjian' },
        { title: '创意团建', code: 'cytuanjian', url: '/cytuanjian' },
        { title: '客户案例', code: 'cases', url: '/cases' },
        { title: '关于我们', code: 'aboutUs', url: '/aboutUs' },
        { title: '免费定制', code: 'getplan', url: '/getplan' },
      ],
    }
  },
  methods: {},
}
</script>

<style scoped lang="scss">
.header {
  width: 100%;
  z-index: 9;
  background: #ffffff;
  padding: 10px;
  box-sizing: border-box;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.05);
  position: fixed;
  top: 0;
  .logo {
    width: 55%;
    position: relative;
    .logo-img {
      width: 100%;
      height: auto;
      display: block;
    }
  }
  .header_nav {
    background: url(~assets/images/header_nva.png) no-repeat;
    background-size: 100% auto;
    width: 5vw;
    height: 5vw;
    position: absolute;
    right: 3.5vw;
    top: 5vw;
    &.close {
      background: url(~assets/images/header_close.png) no-repeat;
      background-size: 90% auto;
    }
  }
  .nav_con {
    position: fixed;
    background: rgba(255, 255, 255, 0.96);
    z-index: 8;
    left: 0;
    right: 0;
    height: 100%;
    display: none;
    .nav {
      width: 100%;
      padding-top: 10px;
      ul li {
        line-height: 8vh;
        text-align: center;
        a {
          font-size: 15px;
          color: #0146a1;
          font-weight: inherit;
          position: relative;
          display: inline-block;
          text-decoration: none;
          &:after {
            content: '';
            position: absolute;
            width: 100%;
            height: 1px;
            left: 0;
            bottom: 1.5vh;
            background: #0146a1;
            display: inline-block;
          }
        }
      }
      .tel {
        text-align: center;
        margin-top: 26px;
        font-weight: 600;
        font-size: 16px;
        color: #017bce;
      }
    }
  }
}
</style>
>
