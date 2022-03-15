<template>
  <main>
    <section class="main-slide">
      <b-container>
        <carousel
          :per-page="1"
          :speed="1000"
          :autoplayTimeout="4500"
          autoplay
          loop
          centerMode
          :paginationSize="150"
          paginationPosition="bottom-overlay"
          :touchDrag="false"
          :mouseDrag="false"
        >
          <slide v-for="item in items" :key="item.id">
            <a
              class="d-block w-100 h-100"
              :href="`#${item.name}`"
              v-smooth-scroll="{ duration: 200, offset: 0 }"
              :style="{ background: item.color }"
            >
              <b-row class="h-100">
                <b-col
                  class="col-6 d-flex justify-content-center align-items-center text-white"
                  :style="{ flexDirection: 'column' }"
                >
                  <div>
                    <p class="text-30 mb-1">{{ item.slide.subTitle }}</p>
                    <h3 class="text-65 fw-900">{{ item.title }}</h3>
                    <span
                      class="text-30 fw-900 py-2 px-4 my-4 d-inline-block"
                      :style="{ border: '1px solid', borderRadius: '2rem' }"
                      >{{ item.slide.pill }}</span
                    >
                    <ul>
                      <li
                        v-for="list in item.slide.description"
                        :key="list.id"
                        class="text-24 fw-700"
                      >
                        {{ list }}
                      </li>
                    </ul>
                  </div>
                </b-col>
              </b-row>
            </a></slide
          >
        </carousel>
      </b-container>
    </section>
    <section
      class="border-top"
      v-for="(item, i) in items"
      :id="item.name"
      :key="item.name"
    >
      <b-container>
        <b-row
          class="text-white"
          :style="{
            background: item.color,
            padding: '4rem',
          }"
        >
          <h2 class="text-50 fw-900">{{ item.title }}</h2>
          <span class="text-30">{{ item.card.subTitle }}</span>
          <ul class="itemStyle my-5">
            <li>
              <span>대출한도</span>
              <div v-html="item.card.condition.limit"></div>
            </li>
            <li>
              <span>대출금리</span>
              <div v-html="item.card.condition.rate"></div>
            </li>
            <li>
              <span>대출기간</span>
              <div v-html="item.card.condition.term"></div>
            </li>
            <li>
              <span>상환방법</span>
              <div v-html="item.card.condition.return"></div>
            </li>
          </ul>
          <b-btn
            class="mt-5"
            variant="white"
            @click="item.detail = !item.detail"
            ><span
              class="text-white py-3 px-5 fw-900 text-20 d-block buttonOver"
              :style="{ border: '1px solid #fff', borderRadius: '2rem' }"
            >
              {{ item.title }}
              <span class="fw-400"
                >상세 가이드 {{ item.detail ? "닫기" : "보기" }}
              </span>
              <font-awesome-icon
                :icon="
                  item.detail ? 'chevron-circle-up' : 'chevron-circle-down'
                "
              />
            </span>
          </b-btn>
        </b-row>
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
    <!-- 상담신청 -->
    <section
      id="inquiry"
      class="w-100"
      :style="{
        background: 'linear-gradient(to top,  #252830 50%, transparent 50%)',
      }"
    >
      <b-container
        class="p-0 bg-black text-white py-5 w-50"
        :style="{ borderRadius: '1.5rem' }"
      >
        <b-row class="text-center mb-5">
          <h2 class="fw-900">
            <span class="border-bottom">간편상담 신청하기</span>
          </h2>
        </b-row>
        <b-row class="m-auto w-50">
          <Inquiry />
        </b-row>
      </b-container>
    </section>
    <GoButton />
  </main>
</template>

<script>
import GoButton from "../Layout/GoButton.vue";
import Inquiry from "../Layout/Inquiry.vue";
import Detail from "../components/Detail.vue";

export default {
  name: "Home",
  components: { GoButton, Inquiry, Detail },
  data() {
    return {
      items: [
        {
          name: "item-1",
          title: "햇살론",
          slide: {
            subTitle: "국가가 지원하는 '정부지원 서민대출'",
            pill: "온라인 햇살론 진행시 비대면 자동심사",
            description: [
              "최저 연 8.69% ~ 최고 연 10.29%",
              "온라인 햇살론 진행시 1.3% 인하",
              "최대 2,000만원까지 가능",
              "중도상환수수료 없음",
            ],
          },
          card: {
            subTitle:
              "저신용, 저소득 서민을 대상으로 지원해주는 보증부 서민대출",
            condition: {
              limit:
                "<p>최대 2,000만원</p><span>최소 600만원~ 최대 2,000만원(개인신용평점별 차등)</span>",
              rate: "<p>최저 연8.69% ~ <br/>최고 연10.29%</p><span>개인신용평점별 차등 매월금융감독원 고시금리에 따라 변동/2022.03.01 기준 온라인 햇살론 진행시 1.3%인하(당일송금가능)</span>",
              term: "<p>3년 또는 5년</p><span>중 택일가능</span>",
              return: "<p>원금균등분할상환</p>",
            },
          },
          detail: false,
          color: "#ff9c01",
        },
        {
          name: "item-2",
          title: "사잇돌2",
          slide: {
            subTitle: "서울보증보험 연계 서민대출",
            pill: "중·저 신용자를 위한 대출",
            description: [
              "최저 연 10.5% ~ 최고 연 19.49%",
              "최대 3,000만원까지 가능",
              "중도상환수수료 없음",
            ],
          },
          card: {
            subTitle: "중·저 신용자를 위한 대출",
            condition: {
              limit:
                "<p>최대 3,000만원</p><span>최소 100만원~ 최대 3,000만원(단, 서울보증보험 승인금액 이내)</span>",
              rate: "<p>최저 연10.5% ~ <br/>최고 연19.49%</p><span>개인신용평점별 차등/기준일: 2022.01.03</span>",
              term: "<p>1년 ~ 5년</p><span>대출기간은 년 단위로 취급가능<p>",
              return: "<p>원금균등분할상환</p>",
            },
          },
          detail: false,
          color: "#0a6e01",
        },
        {
          name: "item-3",
          title: "하나드림론",
          slide: {
            subTitle: "근로소득자를 위한 신용대출",
            pill: "고금리 부담을 줄여드리는 하나드림론",
            description: [
              "최저 연 5.9% ~ 최고 연 19.49%",
              "최대 5,000만원까지 가능",
              "최대 72개월 분할상환",
            ],
          },
          card: {
            subTitle: "근로소득자를 위한 대출",
            condition: {
              limit:
                "<p>최대 5,000만원</p><span>최소 300만원~ 최대 5,000만원 이내</span>",
              rate: "<p>최저 연5.9% ~ <br/>최고 연19.49%</p><span>기준금리+가산금리 (개인신용평점 차등, 2022.01.03 기준)</span>",
              term: "<p>1년 ~ 6년</p><span>대출기간은 년 단위로 취급가능</span>",
              return: "<p>원금균등분할상환</p>",
            },
          },
          detail: false,
          color: "#31c9ee",
        },
        {
          name: "item-4",
          title: "하나슈퍼드림론",
          slide: {
            subTitle: "근로소득자를 위한 신용대출",
            pill: "우량직장인을 위한 대출",
            description: [
              "최저 연 5.9% ~ 최고 연 17.99%",
              "최대 1억원까지 가능",
              "최대 10년 상환",
              "만기일시상환 가능",
            ],
          },
          card: {
            subTitle: "근로소득자를 위한 신용대출",
            condition: {
              limit:
                "<p>최대 1억원</p><span>최소 300만원 ~ 최대 1억원 이내</span>",
              rate: "<p>최저 연5.9% ~ <br/>최고 연17.99%</p><span>기준금리+가산금리 (개인신용평점별 차등, 2022.01.03 기준)</span>",
              term: "<p>1년 ~ 10년</p><span>대출기간은 년 단위로 취급가능</span>",
              return: "<p>원금균등분할상환 <br/>만기일시상환 중 택일</p>",
            },
          },
          detail: false,
          color: "#43b546",
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
