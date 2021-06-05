<template>
  <main>
    <div class="main-banner">
      <img src="~assets/images/banner1.png" alt="" />
      <h4>高山滑雪</h4>
    </div>
    <div class="tit">
      旅行团建
      <span> 将团建放大，让旅行回归 </span>
    </div>
    <div class="filter">
      <van-grid :column-num="2">
        <van-grid-item>
          <van-field
            readonly
            clickable
            name="picker"
            :value="selectedType"
            placeholder="主题玩法"
            @click="showPicker = true"
          />
          <van-popup v-model="showPicker" position="bottom">
            <van-picker
              show-toolbar
              :columns="typeList"
              @confirm="onConfirm"
              @cancel="showPicker = false"
            />
          </van-popup>
        </van-grid-item>
        <van-grid-item></van-grid-item>
      </van-grid>
    </div>
  </main>
</template>
<script>
import { Grid, GridItem, Field, Popup, Picker } from 'vant'
export default {
  components: {
    [Grid.name]: Grid,
    [GridItem.name]: GridItem,
    [Field.name]: Field,
    [Popup.name]: Popup,
    [Picker.name]: Picker,
  },
  data() {
    return {
      showPicker: false,
      typeList: [
        { text: '团建爆款', code: '1' },
        { text: '山河风光', code: '2' },
      ],
      selectedType: '',
    }
  },
  methods: {
    onConfirm(item) {
      this.selectedType = item.text
      this.showPicker = false
    },
  },
}
</script>
<style lang="scss" scoped>
.main-banner {
  overflow: hidden;
  height: 20vh;
  position: relative;
  .img {
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  h4 {
    position: absolute;
    left: 5%;
    right: 5%;
    width: 90%;
    text-align: center;
    top: 50%;
    margin-top: -25px;
    height: 50px;
    line-height: 50px;
    font-size: 25px;
    font-weight: 800;
    color: #fff;
  }
}
.filter {
  padding: 9px 0;
  background: #fff;
  box-sizing: border-box;
  border: solid 1px #ddd;
  border-radius: 5px;
  margin: 10px 16px;
  .van-grid:after {
    border-width: 0;
  }
  /deep/ .van-grid-item__content {
    padding: 0;
    &:after {
      border-width: 0 1px 0 0;
      border-color: #ddd;
    }
  }
  /deep/ .van-cell {
    padding: 0 10px;
    &:after {
      border-width: 0;
    }
  }
}
</style>
