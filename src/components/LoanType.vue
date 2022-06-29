<template>
  <main>
    <!-- 상품 메인 슬라이드 -->
    <section class="main-slide">
      <carousel
        :per-page="1"
        :speed="1000"
        :autoplayTimeout="4500"
        autoplay
        loop
        centerMode
        :paginationSize="15"
        paginationPosition="bottom-overlay"
        paginationActiveColor="#009591"
        paginationColor="rgba(0,0,0,.5)"
        :paginationPadding="15"
      >
        <slide
          v-for="item in items"
          :key="item.name"
          :style="{
            background: `url(${require('@/assets/images/item_00' +
              item.name.charAt(item.name.length - 1) +
              '.png')}) no-repeat center /cover`,
          }"
          class="py-5"
        >
          <b-container class="py-5 gothic">
            <div class="py-5">
              <p class="text-30 mb-1 mainColor">{{ item.subTitle }}</p>
              <h3 class="text-65 mb-3">{{ item.title }}</h3>
              <p class="text-30 mb-5">{{ item.description }}</p>
              <b-btn variant="link" class="p-0 text-decoration-none d-block">
                <a
                  class="mainBg2 text-30 text-decoration-none text-white px-5 py-2"
                  :href="`#${item.name}`"
                  v-smooth-scroll="{ duration: 200, offset: 0 }"
                  >상세안내 보러가기
                  <font-awesome-icon icon="fa-solid fa-caret-down"
                /></a>
              </b-btn>
            </div>
          </b-container>
        </slide>
      </carousel>
    </section>
    <!-- 상담신청 -->
    <section
      id="inquiry"
      class="text-black py-3"
      :style="{
        background: `url(${require('@/assets/images/visual_bg.jpg')}) no-repeat center /cover`,
      }"
    >
      <b-container class="py-5">
        <div class="pb-5">
          <h2 class="gothic text-50 text-center pb-3 mainColor">
            대출상담 신청
          </h2>
          <p class="text-40 text-center gothic">
            <!-- 연락처를 남겨주시면 전문상담원이 연락드립니다. -->
            <span class="text-20 opacity-50 d-block">
              <font-awesome-icon icon="fa-solid fa-asterisk" /> 상담만으로는
              신용조회 기록이 절대 남지 않습니다.
            </span>
          </p>
        </div>
        <InquiryItem />
      </b-container>
    </section>
    <b-container>
      <!-- <b-row class="text-center mb-5">
          <h2 class="fw-900">
            <span>간편상담 신청하기</span>
          </h2>
        </b-row> -->
    </b-container>
    <!-- 상품별 안내 -->
    <article v-for="(item, i) in items" :id="item.name" :key="item.name">
      <!-- 간편설명 -->
      <section class="border-top py-5">
        <b-container>
          <h2 class="text-50 fw-900">{{ item.title }}</h2>
          <span class="text-30">{{ item.description }}</span>
          <b-row class="text-center align-items-end my-5 pt-3">
            <b-col class="border-end">
              <img
                :src="require('@/assets/images/img_rate.png')"
                alt="최저금리"
                class="mb-5"
              />
              <span
                class="text-20 d-block gothic"
                :style="{ color: bgGradient[5] }"
              >
                최저금리
              </span>
              <p class="text-40 gothic r m-0 lh-sm" v-html="item.rate"></p>
            </b-col>
            <b-col class="border-end">
              <img
                :src="require('@/assets/images/img_limit.png')"
                alt="최대한도"
                class="mb-5"
              />
              <span
                class="text-20 d-block gothic"
                :style="{ color: bgGradient[5] }"
              >
                최대한도
              </span>
              <p class="text-40 gothic r m-0 lh-sm" v-html="item.limit"></p>
            </b-col>
            <b-col>
              <img
                :src="require('@/assets/images/img_repay.png')"
                alt="상환기간"
                class="mb-5"
              />
              <span
                class="text-20 d-block gothic"
                :style="{ color: bgGradient[5] }"
              >
                상환기간
              </span>
              <p class="text-40 gothic r m-0 lh-sm" v-html="item.term"></p>
            </b-col>
          </b-row>
          <b-row :style="{ gap: '1rem' }">
            <b-col
              :style="{
                background: `url(${require('@/assets/images/btn_bg_rd.png')}) no-repeat center /cover !important`,
              }"
              class="shadow"
            >
              <b-btn
                class="w-100 text-30 text-decoration-none text-white gothic p-4"
                variant="link"
                to="/inquiry"
              >
                <img
                  :src="require('@/assets/images/ico_headset.png')"
                  alt="상담"
                />
                간편상담 신청하기</b-btn
              >
            </b-col>
            <b-col
              :style="{
                background: `url(${require('@/assets/images/btn_bg_gr.png')}) no-repeat center /cover !important`,
              }"
              class="shadow"
            >
              <b-btn
                class="w-100 text-30 text-decoration-none text-white gothic p-4"
                variant="link"
                @click="item.detail = !item.detail"
              >
                상세안내 {{ item.detail ? "닫기" : "보기" }}
                <font-awesome-icon
                  :icon="
                    item.detail ? 'chevron-circle-up' : 'chevron-circle-down'
                  "
              /></b-btn>
            </b-col>
          </b-row>
        </b-container>
      </section>
      <!-- 상세설명 -->

      <section :style="{ background: bgGradient[0] }">
        <b-container>
          <transition name="fade">
            <b-row v-if="item.detail" class="pt-5">
              <template v-if="i == 0"><Detail :one="true" /></template>
              <template v-if="i == 1"><Detail :two="true" /></template>
              <template v-if="i == 2"><Detail :three="true" /></template>
              <template v-if="i == 3"><Detail :four="true" /></template>
            </b-row>
          </transition>
        </b-container>
      </section>
    </article>
  </main>
</template>

<script>
import InquiryItem from "./InquiryItem.vue";
import Detail from "./Detail.vue";

export default {
  name: "Home",
  components: { InquiryItem, Detail },
  data() {
    return {
      bgGradient: [
        "#eaf2f2",
        "#5cc4b9",
        "#34c0a6",
        "#09c5a2",
        "#139980",
        "#008486",
      ],
      items: [
        {
          name: "item-1",
          title: "행복아파트론",
          subTitle: "무담보! 무설정!",
          description: "아파트소유자 대상 신용대출",
          limit:
            "최대<span class='gothic'>2억</span>원<span class='text-noto text-20'> (최저 300만원)",
          rate: "연 <span class='gothic'>5.9% ~ 16.9%</span>",
          term: "<span class='gothic'>12 ~ 120</span>개월",
          detail: false,
        },
        {
          name: "item-2",
          title: "e하나신용대출",
          subTitle: "소득이 있으면 빠르고 간편하게!",
          description: "소득자 간편이용 인터넷 전용 신용대출",
          limit:
            "최대<span class='gothic'>7,000</span>만원<span class='text-noto text-20'> (최저 300만원)",
          rate: "연 <span class='gothic'>5.9% ~ 18.9%</span>",
          term: "<span class='gothic'>12 ~ 120</span>개월",
          detail: false,
        },
        {
          name: "item-3",
          title: "원큐자동차담보대출",
          subTitle: "내 차는 그대로 타면 돼!",
          description: "자동차 소유자 대상 온라인 담보대출",
          limit:
            "최대<span class='gothic'>1억</span>원<span class='text-noto text-20'> (최저 100만원)",
          rate: "연 <span class='gothic'>4.9% ~ 16.9%</span>",
          term: "<span class='gothic'>12 ~ 120</span>개월",
          detail: false,
        },
        {
          name: "item-4",
          title: "아파트론",
          subTitle: "개인사업자를 위한 상품!",
          description: "아파트소유자 대상 신용대출",
          limit:
            "최대<span class='gothic'>2억</span>원<span class='text-noto text-20'> (최저 300만원)",
          rate: "연 <span class='gothic'>5.9% ~ 16.9%</span>",
          term: "<span class='gothic'>12 ~ 120</span>개월",
          detail: false,
        },
      ],
    };
  },
  methods: {},
};
</script>

<style lang="scss">
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.itemStyle {
  display: flex;
  justify-content: space-between;
  text-align: center;
  color: #000;
  li {
    width: 23%;
    // background: #fff;
    // border-radius: 1rem;
    // padding: 1.5rem;
    > span {
      font-weight: 900;
      font-size: 1.5rem;
      margin-bottom: 1rem;
      display: block;
      color: #fff;
    }
    div {
      box-shadow: 20px 20px 0 rgba(0, 0, 0, 0.2);
      padding: 0 1.5rem;
      background: #fff;
      border-radius: 1rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
      height: 100%;
      p {
        font-size: 1.5rem;
        font-weight: 900;
        margin: 0;
      }
      span {
        font-size: 0.9rem;
      }
    }
  }
}
.buttonOver {
  position: relative;
  overflow: hidden;
  transition: color 0.2s ease-in-out;
  box-shadow: 5px 5px 0;
  z-index: 1;
  &:active {
    position: relative;
    left: 5px;
    top: 5px;
    box-shadow: 0 0 0;
  }
  &::after {
    content: "";
    position: absolute;
    background: #fff;
    width: 100%;
    height: 100%;
    left: 0;
    bottom: -100%;
    transition: bottom 0.2s ease-in-out;
    z-index: -1;
  }
  &:hover {
    color: #000 !important;
    &::after {
      bottom: 0;
    }
  }
}
</style>
