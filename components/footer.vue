<template>
  <footer class="footer">
    <p class="footer-text">
      安吉云谷乡创文旅开发有限公司
      版权所有&nbsp;&nbsp;&nbsp;&nbsp;电话：18757274645
    </p>
  </footer>
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
.footer {
  background: #000;
  padding: 15px 0;
  margin-top: 15px;
  color: #999;
  text-align: center;
  font-size: 14px;
  font-weight: 600;
  .footer-text {
    color: #fff;
    padding: 0 0.34em;
    font-size: 12px;
  }
}
</style>
