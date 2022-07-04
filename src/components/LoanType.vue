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
          class="py-md-5 py-3"
        >
          <b-container class="py-md-5 gothic">
            <div class="py-md-5 py-3">
              <p class="text-md-30 text-20 mb-1 mainColor">
                {{ item.subTitle }}
              </p>
              <h3 class="text-65 mb-3 d-none d-md-block">{{ item.title }}</h3>
              <h3
                class="text-36 mb-3 d-inline-block px-2 d-md-none mainBg text-white"
              >
                {{ item.title }}
              </h3>
              <p class="text-30 mb-md-5 d-none d-md-block">
                {{ item.description }}
              </p>
              <p class="text-20 mb-md-5 d-inline-block px-2 d-md-none bg-white">
                {{ item.description }}
              </p>
              <b-btn
                variant="link"
                class="d-none d-md-block p-0 text-decoration-none"
              >
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
      class="text-black py-md-3"
      :style="{
        background: `url(${require('@/assets/images/visual_bg.jpg')}) no-repeat center /cover`,
      }"
    >
      <b-container class="py-md-5 py-3">
        <div class="pb-md-5">
          <h2 class="gothic text-md-50 text-28 text-center pb-md-3 mainColor">
            대출상담 신청
          </h2>
          <p class="text-md-40 text-center gothic">
            <!-- 연락처를 남겨주시면 전문상담원이 연락드립니다. -->
            <span class="text-md-20 text-15 opacity-50 d-block">
              <font-awesome-icon icon="fa-solid fa-asterisk" /> 상담만으로는
              신용조회 기록이 절대 남지 않습니다.
            </span>
          </p>
        </div>
        <InquiryItem />
      </b-container>
    </section>
    <b-container> </b-container>
    <!-- 상품별 안내 -->
    <article v-for="item in items" :id="item.name" :key="item.name">
      <!-- 간편설명 -->
      <section class="border-top py-md-5 py-3">
        <b-container>
          <div
            class="gothic text-center background-none"
            :style="{
              background: `url(${item.bgImg[0]}) no-repeat left bottom, url(${item.bgImg[1]}) no-repeat right bottom`,
            }"
          >
            <p class="text-md-30 text-24 mb-1 mainColor">{{ item.subTitle }}</p>
            <h3 class="text-md-65 text-30 mb-md-3 mb-1">{{ item.title }}</h3>
            <p class="text-md-30 text-20 mb-md-5 mb-2">
              {{ item.description }}
            </p>
          </div>
          <b-row
            class="text-center align-items-end my-md-5 my-2 pb-md-0 pt-md-3 pb-3 pt-3 home-icons"
          >
            <b-col class="border-end p-0" cols="4" md="">
              <img
                :src="require('@/assets/images/img_rate.png')"
                alt="최저금리"
                class="mb-md-5 mb-2"
              />
              <span
                class="text-md-20 text-18 d-block gothic"
                :style="{ color: bgGradient[5] }"
              >
                최저금리
              </span>
              <p
                class="text-md-40 text-20 gothic r m-0 lh-sm"
                v-html="item.rate"
              ></p>
            </b-col>
            <b-col class="border-end p-0" cols="4" md="">
              <img
                :src="require('@/assets/images/img_limit.png')"
                alt="최대한도"
                class="mb-md-5 mb-2"
              />
              <span
                class="text-md-20 text-18 d-block gothic"
                :style="{ color: bgGradient[5] }"
              >
                최대한도
              </span>
              <p
                class="text-md-40 text-20 gothic r m-0 lh-sm"
                v-html="item.limit"
              ></p>
            </b-col>
            <b-col class="p-0" cols="4" md="">
              <img
                :src="require('@/assets/images/img_repay.png')"
                alt="상환기간"
                class="mb-md-5 mb-2"
              />
              <span
                class="text-md-20 text-18 d-block gothic"
                :style="{ color: bgGradient[5] }"
              >
                상환기간
              </span>
              <p
                class="text-md-40 text-20 gothic r m-0 lh-sm"
                v-html="item.term"
              ></p>
            </b-col>
          </b-row>
          <b-row :style="{ gap: '1rem' }">
            <b-col
              :style="{
                background: `url(${require('@/assets/images/btn_bg_rd.png')}) no-repeat center /cover !important`,
              }"
              class="shadow d-none d-md-inline-block"
            >
              <b-btn
                class="w-100 text-md-30 text-decoration-none text-white gothic p-md-4"
                variant="link"
                to="/inquiry"
              >
                <img
                  :src="require('@/assets/images/ico_headset.png')"
                  alt="상담"
                  class="d-none d-md-inline-block"
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
                class="w-100 text-md-30 text-decoration-none text-white gothic p-md-4"
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
          <transition name="fade" v-if="item.detail">
            <article class="py-md-5 py-4">
              <h2 class="hana b text-25 text-center pb-md-3">
                <span class="mainColor">{{ item.title }}</span> 상품안내
              </h2>
              <b-row class="gy-md-4 gy-2">
                <b-col cols="12" md="6">
                  <b-row
                    class="align-items-center h-100 rounded bg-white p-md-4 p-3"
                    :style="{ border: '1px solid #cdcdcd' }"
                  >
                    <h3 class="hana b mainColor2 text-md-25 text-22 mb-3">
                      대출대상
                    </h3>
                    <div
                      v-html="item.detailDescription.target"
                      class="m-0 text-20"
                    ></div>
                  </b-row>
                </b-col>
                <b-col cols="12" md="6">
                  <b-row
                    class="align-items-center h-100 rounded bg-white p-md-4 p-3"
                    :style="{ border: '1px solid #cdcdcd' }"
                  >
                    <h3 class="hana b mainColor2 text-md-25 text-22 mb-3">
                      상환방법
                    </h3>
                    <div
                      v-html="item.detailDescription.repay"
                      class="m-0 text-20"
                    ></div>
                  </b-row>
                </b-col>
                <b-col cols="12" md="6">
                  <b-row
                    class="align-items-center h-100 rounded bg-white p-md-4 p-3"
                    :style="{ border: '1px solid #cdcdcd' }"
                  >
                    <h3 class="hana b mainColor2 text-md-25 text-22 mb-3">
                      중도상환수수료
                    </h3>
                    <div
                      v-html="item.detailDescription.prepayment"
                      class="m-0 text-20"
                    ></div>
                  </b-row>
                </b-col>
                <b-col cols="12" md="6">
                  <b-row
                    class="align-items-center h-100 rounded bg-white p-md-4 p-3"
                    :style="{ border: '1px solid #cdcdcd' }"
                  >
                    <h3 class="hana b mainColor2 text-md-25 text-22 mb-3">
                      연체이자율
                    </h3>
                    <div
                      v-html="item.detailDescription.overdue"
                      class="m-0 text-20"
                    ></div>
                  </b-row>
                </b-col>
                <b-col cols="12" md="6">
                  <b-row
                    class="align-items-center h-100 rounded bg-white p-md-4 p-3"
                    :style="{ border: '1px solid #cdcdcd' }"
                  >
                    <h3 class="hana b mainColor2 text-md-25 text-22 mb-3">
                      이자부과시기
                    </h3>
                    <div
                      v-html="item.detailDescription.imposition"
                      class="m-0 text-20"
                    ></div>
                  </b-row>
                </b-col>
                <!-- 저당설정 -->
                <b-col cols="12" md="6" v-if="item.detailDescription.mortgage">
                  <b-row
                    class="align-items-center h-100 rounded bg-white p-md-4 p-3"
                    :style="{ border: '1px solid #cdcdcd' }"
                  >
                    <h3 class="hana b mainColor2 text-md-25 text-22 mb-3">
                      저당설정
                    </h3>
                    <div
                      v-html="item.detailDescription.mortgage"
                      class="m-0 text-20"
                    ></div>
                  </b-row>
                </b-col>
              </b-row>
            </article>
          </transition>
        </b-container>
      </section>
    </article>
  </main>
</template>

<script>
import InquiryItem from "./InquiryItem.vue";

export default {
  name: "Home",
  components: { InquiryItem },
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
            "<span class='d-none d-md-inline-block'>최대</span><span class='gothic'>2억</span>원<span class='text-noto text-20 d-none d-md-inline-block'> (최저 300만원)</span>",
          rate: "연 <span class='gothic'>5.9% <span class='d-none d-md-inline-block'>~ 16.9%</span></span>",
          term: "<span class='gothic'><span class='d-none d-md-inline-block'>12 ~ </span>120</span>개월",
          detail: true,
          detailDescription: {
            // 대상
            target: "아파트를 소유한 손님(본인 또는 배우자 공동명의)",
            // 상환방법
            repay: "원리금균등분할상환만기일시상환(당사 기준 충족 시)",
            // 중도상환수수료
            prepayment:
              "대출실행일 기준 경과기간에 따라 차등 적용되며, 3년 경과시 면제 ※ 중도상환수수료율 : 2%",
            // 연체이자율
            overdue: "약정이율 + 3%(법정최고금리 연 20% 이내)",
            // 이자부과시기
            imposition: "매월 후취",
          },
          bgImg: [
            require("@/assets/images/town1.svg"),
            require("@/assets/images/town2.svg"),
          ],
        },
        {
          name: "item-2",
          title: "e하나신용대출",
          subTitle: "소득이 있으면 빠르고 간편하게!",
          description: "소득자 간편이용 인터넷 전용 신용대출",
          limit:
            "<span class='d-none d-md-inline-block'>최대</span><span class='gothic'>7,000</span>만원<span class='text-noto text-20 d-none d-md-inline-block'> (최저 300만원)</span>",
          rate: "연 <span class='gothic'>5.9% <span class='d-none d-md-inline-block'>~ 18.9%</span></span>",
          term: "<span class='gothic'><span class='d-none d-md-inline-block'>12 ~ </span>120</span>개월",
          detail: true,
          detailDescription: {
            // 대상
            target: "재직기간 6개월 이상 직장인 그 외 당사기준 충족 손님",
            // 상환방법
            repay: "원리금균등분할상환",
            // 중도상환수수료
            prepayment: "없음",
            // 연체이자율
            overdue: "약정이율 + 3% (법정최고금리 연 20% 이내)",
            // 이자부과시기
            imposition: "매월 후취",
          },
          bgImg: [
            require("@/assets/images/money1.svg"),
            require("@/assets/images/money2.svg"),
          ],
        },
        {
          name: "item-3",
          title: "원큐자동차담보대출",
          subTitle: "내 차는 그대로 타면 돼!",
          description: "자동차 소유자 대상 온라인 담보대출",
          limit:
            "<span class='d-none d-md-inline-block'>최대</span><span class='gothic'>1억</span>원<span class='text-noto text-20 d-none d-md-inline-block'> (최저 100만원)</span>",
          rate: "연 <span class='gothic'>4.9% <span class='d-none d-md-inline-block'>~ 16.9%</span></span>",
          term: "<span class='gothic'><span class='d-none d-md-inline-block'>12 ~ </span>120</span>개월",
          detail: true,
          detailDescription: {
            // 대상
            target: "본인명의 차량 3개월 이상 소유자(출고 10년 이내로 제한)",
            // 상환방법
            repay: "원리금균등분할상환",
            // 저당설정
            mortgage: "당사 1순위 설정(차량시세의 최대 80% 설정)",
            // 중도상환수수료
            prepayment:
              "대출실행일 기준 경과기간에 따라 차등 적용되며, 3년 경과시 면제 ※ 중도상환수수료율 : 2%",
            // 연체이자율
            overdue: "약정이율 + 3% (법정최고금리 연 20% 이내)",
            // 이자부과시기
            imposition: "매월 후취",
          },
          bgImg: [
            require("@/assets/images/car1.svg"),
            require("@/assets/images/car2.svg"),
          ],
        },
        {
          name: "item-4",
          title: "아파트론",
          subTitle: "개인사업자를 위한 상품!",
          description: "아파트소유자 대상 신용대출",
          limit:
            "<span class='d-none d-md-inline-block'>최대</span><span class='gothic'>2억</span>원<span class='text-noto text-20 d-none d-md-inline-block'> (최저 300만원)</span>",
          rate: "연 <span class='gothic'>5.9% <span class='d-none d-md-inline-block'>~ 16.9%</span></span>",
          term: "<span class='gothic'><span class='d-none d-md-inline-block'>12 ~ </span>120</span>개월",
          detail: true,
          detailDescription: {
            // 대상
            target: "아파트를 소유한 손님(본인 또는 배우자 공동명의)",
            // 상환방법
            repay: "원리금균등분할상환",
            // 중도상환수수료
            prepayment:
              "대출실행일 기준 경과기간에 따라 차등 적용되며, 3년 경과시 면제 ※ 중도상환수수료율 : 2%",
            // 연체이자율
            overdue: "약정이율 + 3% (법정최고금리 연 20% 이내)",
            // 이자부과시기
            imposition: "매월 후취",
          },
          bgImg: [
            require("@/assets/images/town3.svg"),
            require("@/assets/images/town4.svg"),
          ],
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
</style>
