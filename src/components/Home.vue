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
      class="border-bottom"
      v-for="(item, i) in items"
      :id="item.name"
      :key="item.name"
    >
      <b-container class="">
        <b-row
          class="text-white"
          :style="{
            background: item.color,
            borderRadius: '1rem',
            padding: '4rem',
          }"
        >
          <h2 class="text-50 fw-900">{{ item.title }}</h2>
          <span class="text-30">{{ item.card.subTitle }}</span>
          <ul class="itemStyle my-5">
            <li>
              <span>대출한도</span>
              <div>
                <p>
                  {{ item.card.condition.limit[0] }}
                </p>
                <span>
                  {{ item.card.condition.limit[1] }}
                </span>
              </div>
            </li>
            <li>
              <span>대출금리</span>
              <div>
                <p>
                  {{ item.card.condition.rate[0] }}
                </p>
                <span>
                  {{ item.card.condition.rate[1] }}
                </span>
              </div>
            </li>
            <li>
              <span>대출기간</span>
              <div>
                <p>
                  {{ item.card.condition.term[0] }}
                </p>
                <span>
                  {{ item.card.condition.term[1] }}
                </span>
              </div>
            </li>
            <li>
              <span>상환방법</span>
              <div>
                <p>
                  {{ item.card.condition.return }}
                </p>
              </div>
            </li>
          </ul>
          <b-btn variant="white" @click="item.detail = !item.detail"
            ><span
              class="text-white py-3 px-5 fw-900 text-20"
              :style="{ border: '1px solid #fff', borderRadius: '2rem' }"
            >
              {{ item.title }} 상세 가이드 보기
              <font-awesome-icon
                :icon="
                  item.detail ? 'chevron-circle-up' : 'chevron-circle-down'
                "
              />
            </span>
          </b-btn>
        </b-row>
        <b-row v-if="item.detail">
          <template v-if="i == 0"><Detail :one="true" /></template>
          <template v-if="i == 1"><Detail :two="true" /></template>
          <template v-if="i == 2"><Detail :three="true" /></template>
          <template v-if="i == 3"><Detail :four="true" /></template>
        </b-row>
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
              limit: [
                "최대 2,000만원",
                "최소 600만원~ 최대 2,000만원(개인신용평점별 차등)",
              ],
              rate: [
                "최저 연8.69% ~ 최고 연10.29%",
                "개인신용평점별 차등 매월금융감독원 고시금리에 따라 변동/2022.03.01 기준 온라인 햇살론 진행시 1.3%인하(당일송금가능)",
              ],
              term: ["3년 또는 5년", "중 택일가능"],
              return: "원금균등분할상환",
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
              limit: [
                "최대 3,000만원",
                "최소 100만원~ 최대 3,000만원(단, 서울보증보험 승인금액 이내)",
              ],
              rate: [
                "최저 연10.5% ~ 최고 연19.49%",
                "개인신용평점별 차등/기준일: 2022.01.03",
              ],
              term: ["1년 ~ 5년", "대출기간은 년 단위로 취급가능"],
              return: "원금균등분할상환",
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
              limit: ["최대 5,000만원", "최소 300만원~ 최대 5,000만원 이내"],
              rate: [
                "최저 연5.9% ~ 최고 연19.49%",
                "기준금리+가산금리 (개인신용평점 차등, 2022.01.03 기준)",
              ],
              term: ["1년 ~ 6년", "대출기간은 년 단위로 취급가능"],
              return: "원금균등분할상환",
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
              limit: ["최대 1억원", "최소 300만원 ~ 최대 1억원 이내"],
              rate: [
                "최저 연5.9% ~ 최고 연17.99%",
                "기준금리+가산금리 (개인신용평점별 차등, 2022.01.03 기준)",
              ],
              term: ["1년 ~ 10년", "대출기간은 년 단위로 취급가능"],
              return: "원금균등분할상환 만기일시상환 중 택일",
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

<style lang="scss" scoped>
.itemStyle {
  display: flex;
  justify-content: space-between;
  text-align: center;
  color: #000;
  li {
    width: 20%;
    background: #fff;
    border-radius: 1rem;
    padding: 1.5rem;
    > span {
      font-weight: 900;
      font-size: 1.2rem;
    }
    div {
      display: flex;
      flex-direction: column;
      justify-content: center;
      height: 100%;
      p {
        margin: 0;
        font-size: 1.5rem;
        font-weight: 900;
      }
    }
  }
}
</style>
