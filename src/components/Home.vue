<template>
  <main>
    <section class="border-bottom main-slide">
      <b-container>
        <carousel
          :per-page="1"
          :speed="1000"
          :autoplayTimeout="5000"
          autoplay
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
                    <p class="text-30 mb-1">{{ item.subTitle }}</p>
                    <h3 class="text-65 fw-900">{{ item.title }}</h3>
                    <span
                      class="text-30 fw-900 py-2 px-4 my-4 d-block"
                      :style="{ border: '1px solid', borderRadius: '2rem' }"
                      >{{ item.pill }}</span
                    >
                    <ul>
                      <li v-for="list in item.description" :key="list.id">
                        {{ list }}
                      </li>
                    </ul>
                  </div>
                </b-col>
                <b-col
                  class="col-6"
                  :style="{ background: item.color, filter: 'brightness(1.2)' }"
                ></b-col>
              </b-row> </a
          ></slide>
        </carousel>
      </b-container>
    </section>
    <section
      class="border-bottom"
      v-for="item in items"
      :id="item.name"
      :key="item.name"
    >
      <b-container class="">
        <b-row
          class=""
          :style="{
            background: item.color,
            borderRadius: '1rem',
            padding: '2rem',
          }"
        >
          <h2 class="text-50">{{ item.title }}</h2>
          <b-btn @click="item.detail = !item.detail">{{
            item.detail ? "hide" : "Show"
          }}</b-btn>
        </b-row>
        <b-row v-if="item.detail">{{
          item.name == "item-1" ? "d" : "ㄴㄴ"
        }}</b-row>
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

export default {
  name: "Home",
  components: { GoButton, Inquiry },
  data() {
    return {
      items: [
        {
          name: "item-1",
          title: "햇살론",
          subTitle: "국가가 지원하는 '정부지원 서민대출'",
          pill: "온라인 햇살론 진행시 비대면 자동심사",
          description: [
            "최저 연 8.69% ~ 최고 연 10.29%",
            "온라인 햇살론 진행시 1.3% 인하",
            "최대 2,000만원까지 가능",
            "중도상환수수료 없음",
          ],
          detail: false,
          color: "#ff9c01",
        },
        {
          name: "item-2",
          title: "사잇돌2",
          subTitle: "서울보증보험 연계 서민대출",
          pill: "중·저 신용자를 위한 대출",
          description: [
            "최저 연 10.5% ~ 최고 연 19.49%",
            "최대 3,000만원까지 가능",
            "중도상환수수료 없음",
          ],
          detail: false,
          color: "#0a6e01",
        },
        {
          name: "item-3",
          title: "하나드림론",
          subTitle: "근로소득자를 위한 신용대출",
          pill: "고금리 부담을 줄여드리는 하나드림론",
          description: [
            "최저 연 5.9% ~ 최고 연 19.49%",
            "최대 5,000만원까지 가능",
            "최대 72개월 분할상환",
          ],
          detail: false,
          color: "#31c9ee",
        },
        {
          name: "item-4",
          title: "하나슈퍼드림론",
          subTitle: "근로소득자를 위한 신용대출",
          pill: "우량직장인을 위한 대출",
          description: [
            "최저 연 5.9% ~ 최고 연 17.99%",
            "최대 1억원까지 가능",
            "최대 10년 상환",
            "만기일시상환 가능",
          ],
          detail: false,
          color: "#43b546",
        },
      ],
    };
  },
  methods: {},
};
</script>

<style lang="scss" scoped></style>
