<template>
  <main>
    <swiper :options="swiperOptions" class="banner">
      <swiper-slide v-for="(item, index) in swiperList" :key="index">
        <img :src="item.img" alt="" />
        <p>{{ item.text }}</p>
      </swiper-slide>
      <div slot="pagination" ref="pagination" class="swiper-pagination"></div>
    </swiper>
    <div class="ind-col">
      <div class="tit">团建服务内容 <span></span></div>
      <van-grid>
        <van-grid-item v-for="(item, index) in serviceContentList" :key="index">
          <div class="weui-grid__icon">
            <img :src="item.logoSrc" alt="" />
          </div>
          <p class="weui-grid__label">{{ item.title }}</p>
          <p class="weui-msg__desc">{{ item.des }}</p>
        </van-grid-item>
      </van-grid>
    </div>
    <div class="ind-co2">
      <div class="tit">我们的境界<span>团建个性化定制服务商</span></div>
      <swiper
        :options="{
          loop: true,
          slidesPerView: 2.5,
          spaceBetween: 16,
        }"
      >
        <swiper-slide v-for="(item, index) in stateList" :key="index">
          <img :src="item.imgSrc" alt="" />
          <h5>{{ item.title }}</h5>
          <div class="weui-tex">
            <p>{{ item.des }}</p>
          </div>
        </swiper-slide>
      </swiper>
    </div>
    <div class="ind-co3">
      <div class="tit">团建定制方案</div>
      <swiper
        :options="{
          loop: true,
          slidesPerView: 1.2,
          spaceBetween: 16,
          pagination: {
            el: '.swiper-pagination3',
          },
        }"
      >
        <swiper-slide v-for="(item, index) in planList" :key="index">
          <h5>{{ item.title }}</h5>
          <div class="weui-tex weui-tex__5">
            <p>{{ item.desc }}</p>
          </div>
          <div class="label">
            <a v-for="(tag, tagIndex) in item.tagList" :key="tagIndex">
              {{ tag }}
            </a>
          </div>
        </swiper-slide>
        <div
          ref="pagination3"
          slot="pagination"
          class="swiper-pagination swiper-pagination3"
        ></div>
      </swiper>
    </div>
    <div class="ind-co4">
      <div class="tit">
        我们的优势
        <span>
          精益求精，专业靠谱的团建策划师。精心打磨，亲自体验的团建产品。
        </span>
      </div>
      <van-grid :column-num="2">
        <van-grid-item v-for="(item, index) in advantageList" :key="index">
          <div class="weui-grid__icon">
            <img :src="item.imgSrc" alt="" />
          </div>
          <p class="weui-grid__label">{{ item.title }}</p>
          <p class="weui-msg__desc">
            {{ item.desc }}
          </p>
        </van-grid-item>
      </van-grid>
    </div>
    <div class="ind-co5">
      <div class="tit">
        客户案例
        <span> 累计800+成功服务案例 </span>
      </div>
      <swiper
        :options="{
          loop: true,
          slidesPerView: 2.2,
          spaceBetween: 16,
          pagination: {
            el: '.swiper-pagination5',
          },
        }"
      >
        <swiper-slide v-for="(item, index) in caseList" :key="index">
          <a>
            <img :src="item.imgSrc" alt="" />
            <div class="weui-tex weui-tex__3">
              {{ item.desc }}
            </div>
          </a>
        </swiper-slide>
        <div
          ref="pagination3"
          slot="pagination"
          class="swiper-pagination swiper-pagination5"
        ></div>
      </swiper>
      <a href="/cases" class="btn">查看更多</a>
    </div>
    <div class="ind-co6">
      <div class="tit">合作伙伴 <span>他们选择云谷团建</span></div>
      <div class="cooperative">
        <ul class="clearfix">
          <li v-for="(item, index) in cooperateList" :key="index">
            <img :src="item.imgSrc" alt="" />
          </li>
        </ul>
      </div>
    </div>
  </main>
</template>

<script>
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import { Grid, GridItem } from 'vant'
import 'swiper/dist/css/swiper.min.css'
export default {
  components: {
    Swiper,
    SwiperSlide,
    [Grid.name]: Grid,
    [GridItem.name]: GridItem,
  },
  data() {
    return {
      swiperOptions: {
        autoplay: {
          delay: 3000,
          stopOnLastSlide: false,
          disableOnInteraction: true,
        },
        loop: true,
        pagination: {
          el: '.swiper-pagination',
        },
      },
      swiperList: [
        {
          img: require('../assets/images/ind-banner1.png'),
          text: '优质的服务让您轻松出行',
        },
        {
          img: require('../assets/images/ind-banner2.png'),
          text: '优质的服务让您轻松出行',
        },
      ],
      serviceContentList: [
        {
          logoSrc: require('../assets/images/index-col1-1.png'),
          title: '方案策划',
          des: '1对1专属定制师策划',
        },
        {
          logoSrc: require('../assets/images/index-col1-2.png'),
          title: '方案策划',
          des: '多样化场地资源满足多种需求',
        },
        {
          logoSrc: require('../assets/images/index-col1-3.png'),
          title: '旅游服务',
          des: '一站式出行解决方案',
        },
        {
          logoSrc: require('../assets/images/index-col1-4.png'),
          title: '执行人员',
          des: '专业贴心的团建服务',
        },
        {
          logoSrc: require('../assets/images/index-col1-5.png'),
          title: '住宿预订',
          des: '精品名宿/星级酒店/房车',
        },
        {
          logoSrc: require('../assets/images/index-col1-6.png'),
          title: '餐饮安排',
          des: '烧烤/晚宴.农家菜/土灶',
        },
        {
          logoSrc: require('../assets/images/index-col1-7.png'),
          title: '增值服务',
          des: '摄影航拍/团建游记/团建设计',
        },
        {
          logoSrc: require('../assets/images/index-col1-8.png'),
          title: '赠送服务',
          des: '从细节到整体的非凡体验',
        },
      ],
      stateList: [
        {
          imgSrc: require('../assets/images/index-col2-1.png'),
          title: '心灵的温度',
          des: '由一群互联网媒体人、资深人力资源顾问、旅游策划师、视觉vi设计师、环球摄影师，企业内训师等90后构成的年轻创始团队，懂玩法，更会嗨。',
        },
        {
          imgSrc: require('../assets/images/index-col2-2.png'),
          title: '视野的广度',
          des: '团建策划公司拓展训练从企业需求出发，改变传统的团建形式与内容，进行产品的迭代和创新，研发符合年轻企业的主题玩法和创意团建，匹配企业文化个性化定制，为团队赋能。',
        },
        {
          imgSrc: require('../assets/images/index-col2-3.png'),
          title: '思想的深度',
          des: '团建不仅仅是一群人吃喝玩乐，基于员工在团建中的表现，致力于为企业建立科学的人才培养数据模型，改善雇主品牌与员工之间的关系，打造友爱，活跃，合作的企业文化，是我们共同的愿景。',
        },
        {
          imgSrc: require('../assets/images/index-col2-4.png'),
          title: '灵魂的高度',
          des: '云谷团建拥有专业的导师顾问为团建活动提供强大的支持，企业商学院讲师，人文心理学导师，企业一线高管都是我们的团建活动咨询顾问。',
        },
        {
          imgSrc: require('../assets/images/index-col2-5.png'),
          title: '行动的速度',
          des: '专业可靠的执行人员是一次完美上海团建的必备，云谷团建活动方案执行团队拥有多场的团建现场执行经验，领队，教练，项目经理专业靠谱，为团建保驾护航。',
        },
        {
          imgSrc: require('../assets/images/index-col2-6.png'),
          title: '心灵的温度',
          des: '我们从注重上海/苏州/杭州团建中的每一个细节，从团建方案策划到项目执行，竭尽全力的为每一位用户提供贴心周到的安排，将用户体验和口碑放在第一',
        },
      ],
      planList: [
        {
          title: '旅行团建',
          desc: '精选全球小众的旅行目的地，结合当地特色的风景人文，加入趣味的团建环节，让旅行不再走马观花，用一种年轻的方式，点燃团队的热情，完成一次非凡的旅行团建。',
          tagList: ['山河风光', '民宿休闲', '浪漫海岛', '趣味定向'],
        },
        {
          title: '创意团建',
          desc: '专业团建策划公司融入创意的主题玩法，提供定制化团建方案，解决千篇一律的公司团建方式，让上海公司团建、杭州团建等变得充满趣味和新鲜感。',
          tagList: [
            '城市休闲团建',
            '创意主题团建',
            '趣味体育团建',
            '人文心理团建',
          ],
        },
      ],
      advantageList: [
        {
          imgSrc: require('../assets/images/index-col4-1.png'),
          title: '快速响应',
          desc: '我们追求时间的领先，以最快的速度响应客户需求，并提供有效的解决方案。',
        },
        {
          imgSrc: require('../assets/images/index-col4-2.png'),
          title: '精准定位',
          desc: '全面深入了解活动需求、活动目的及行业特性，让活动更有价值。',
        },
        {
          imgSrc: require('../assets/images/index-col4-3.png'),
          title: '专注高效',
          desc: '因为我们一直专注于活动行业，所以我们能更专业、更高效地为企业提供服务。',
        },
        {
          imgSrc: require('../assets/images/index-col4-4.png'),
          title: '极致创意',
          desc: '资深的创意风暴团队，为每个活动策划方案保驾护航，我们的追求是让活动更完美。',
        },
        {
          imgSrc: require('../assets/images/index-col4-5.png'),
          title: '匠心执行',
          desc: '用匠人的态度雕琢执行活动的每一个环节，我们深知成功执行才能让创意方案凸显价值。',
        },
        {
          imgSrc: require('../assets/images/index-col4-6.png'),
          title: '性价比高',
          desc: '多年的战略资源整合优势及采用成熟的成本控制体系，同样的价格我们在品质上更有保障。',
        },
      ],
      caseList: [
        {
          imgSrc: require('../assets/images/index-col4-1.png'),
          desc: '宁波高美厨具团建',
        },
        {
          imgSrc: require('../assets/images/index-col4-2.png'),
          desc: '杭州银行安吉团建行',
        },
      ],
      cooperateList: [
        { imgSrc: require('../assets/images/index-col6-1.png') },
        { imgSrc: require('../assets/images/index-col6-1.png') },
        { imgSrc: require('../assets/images/index-col6-1.png') },
        { imgSrc: require('../assets/images/index-col6-1.png') },
        { imgSrc: require('../assets/images/index-col6-1.png') },
        { imgSrc: require('../assets/images/index-col6-1.png') },
        { imgSrc: require('../assets/images/index-col6-1.png') },
        { imgSrc: require('../assets/images/index-col6-1.png') },
      ],
    }
  },
  computed: {
    swiper() {
      return this.$refs.mySwiper.$swiper
    },
  },
}
</script>

<style scoped lang="scss">
.swiper-container {
  padding: 0px 0 40px 0;
}
main {
  .swiper-container {
    img {
      display: block;
      width: 100%;
    }
  }
  .swiper-container.banner {
    padding: 0;
    .swiper-slide {
      position: relative;
      p {
        position: absolute;
        left: 0;
        top: 50%;
        margin-top: -15px;
        width: 100%;
        height: 30px;
        line-height: 30px;
        font-size: 5.6vw;
        font-weight: 800;
        color: #ffffff;
        letter-spacing: 1.52px;
        text-align: center;
      }
    }
  }
  .ind-col {
    margin: 16px 0;
    .van-grid {
      .weui-grid__icon {
        width: 50px;
        height: 50px;
        overflow: hidden;
        font-size: 14px;
        color: #999;
        img {
          width: 100%;
          height: 100%;
          object-fit: cover;
          display: block;
        }
      }
      .weui-grid__label {
        font-size: 15px;
        font-weight: 300;
        margin: 8px 0;
        display: block;
        color: #000;
        white-space: nowrap;
        text-overflow: ellipsis;
        overflow: hidden;
      }
      .weui-msg__desc {
        line-height: 20px;
        height: 60px;
        text-align: center;
        font-size: 14px;
        color: #999;
      }
    }
  }
  .ind-co2 {
    background: url(~assets/images/index-col2.png) center top no-repeat;
    background-size: cover;
    padding: 10px 16px;
    .tit {
      color: #ffffff;
      span {
        color: #ffffff;
      }
    }
    .swiper-container {
      position: relative;
      padding: 0;
      width: 100%;
      .swiper-slide {
        padding-bottom: 20px;
        img {
          border-radius: 5px;
          margin-bottom: -30px;
        }
        h5 {
          font-size: 16px;
          font-weight: 600;
          color: #fff;
          letter-spacing: 2px;
          padding-left: 16px;
          margin-bottom: 10px;
        }
        .weui-tex {
          font-size: 12px;
          font-weight: 300;
          line-height: 26px;
          color: #fff;
          padding: 0 0 0 16px;
        }
      }
    }
  }
  .ind-co3 {
    border-bottom: solid 10px #f8f8f8;
    padding: 16px 0 16px 16px;
    .swiper-slide {
      border: 1px solid #eeeeee;
      box-shadow: 0 10px 20px 0 rgba(0, 61, 162, 0.1);
      border-radius: 8px;
      padding: 16px;
      box-sizing: border-box;
      h5 {
        font-size: 16px;
        color: #333333;
        letter-spacing: 2px;
        &:after {
          content: '';
          width: 19px;
          height: 1.5px;
          background: #0146a1;
          display: block;
          margin: 10px 0;
        }
      }
      .weui-tex {
        height: 130px;
        * {
          font-size: 12px;
          font-weight: 300;
          line-height: 26px;
          color: #666;
          padding: 0;
        }
      }
      .label {
        height: 70px;
        a {
          display: inline-block;
          font-size: 12px;
          font-weight: 300;
          margin: 0 10px 8px 0;
          background: rgba(0, 181, 255, 0.1);
          border-radius: 4px;
          padding: 3px 8px;
          color: #00b5ff;
        }
      }
    }
    .swiper-pagination-bullets {
      bottom: 10px;
      left: 0;
      width: 100%;
    }
  }
  .ind-co4 {
    border-bottom: solid 10px #f8f8f8;
    padding: 16px;
    .van-grid {
      .weui-grid__icon {
        width: 50px;
        height: 50px;
      }
      .weui-grid__label {
        font-size: 15px;
        font-weight: 300;
        margin: 8px 0;
        display: block;
        color: #000;
        white-space: nowrap;
        text-overflow: ellipsis;
        overflow: hidden;
      }
      .weui-msg__desc {
        line-height: 23px;
        height: 90px;
        text-align: center;
        font-size: 14px;
        color: #999;
      }
    }
  }
  .ind-co5 {
    border-bottom: solid 10px #f8f8f8;
    padding: 16px 0 16px 16px;
    .swiper-slide {
      img {
        width: 100%;
        height: 40vw;
        object-fit: cover;
        border-radius: 5px;
      }
      .weui-tex {
        font-size: 15px;
        line-height: 24px;
        font-weight: 300;
        color: #555;
        margin: 8px 0;
        height: 72px;
      }
    }
  }
  .ind-co6 {
    padding: 16px 0;
    .cooperative {
      ul {
        padding: 0;
        li {
          float: left;
          width: 25%;
          img {
            display: block;
            width: 100%;
          }
        }
      }
    }
  }
}

.weui-tex {
  overflow: hidden;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  font-weight: normal;
  white-space: normal !important;
  word-break: break-all !important;
  * {
    -webkit-box-orient: horizontal;
    width: auto;
    display: inline !important;
    padding: 0;
    margin: 0;
    font-weight: 600 !important;
    white-space: normal !important;
    word-break: break-all !important;
  }
}

.weui-tex__5 {
  -webkit-line-clamp: 5;
}
.weui-tex__3 {
  -webkit-line-clamp: 3;
}
.weui-grid {
  padding: 16px;
}
</style>
