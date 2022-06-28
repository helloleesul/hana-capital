<template>
  <main>
    <!-- 편한아파트론 메인-->
    <section
      class="text-black border-bottom py-3"
      :style="{
        background: `url(${require('@/assets/images/visual_bg.jpg')}) no-repeat center /cover`,
      }"
    >
      <b-container class="py-5">
        <h2 class="hana b text-30 text-center pb-3 mainColor">편한아파트론</h2>
        <p class="text-50 text-center gothic lh-sm">
          쉽다! 빠르다! 아파트소유자 신용대출 <br />
          <span :style="{ color: bgGradient[5] }">저당 설정없이 </span>
          <span :style="{ color: bgGradient[2] }">넉넉한 한도!</span>
        </p>
        <b-row class="text-center align-items-end my-5 pt-3">
          <b-col class="border-end">
            <img
              :src="require('@/assets/images/img_rate.png')"
              alt="최저금리"
              class="mb-5"
            />
            <p class="text-40 gothic r m-0 lh-sm">
              <span
                class="text-20 d-block gothic"
                :style="{ color: bgGradient[5] }"
              >
                최저금리
              </span>
              연 <span class="gothic">7.9%</span>
            </p>
          </b-col>
          <b-col class="border-end">
            <img
              :src="require('@/assets/images/img_limit.png')"
              alt="최대한도"
              class="mb-5"
            />
            <p class="text-40 gothic r m-0 lh-sm">
              <span
                class="text-20 d-block gothic"
                :style="{ color: bgGradient[5] }"
              >
                최대한도
              </span>
              <span class="gothic">1억 5,000</span>만원
            </p>
          </b-col>
          <b-col>
            <img
              :src="require('@/assets/images/img_repay.png')"
              alt="상환기간"
              class="mb-5"
            />
            <p class="text-40 gothic r m-0 lh-sm">
              <span
                class="text-20 d-block gothic"
                :style="{ color: bgGradient[5] }"
              >
                상환기간
              </span>
              최대<span class="gothic">160</span>개월
            </p>
          </b-col>
        </b-row>
        <b-row :style="{ gap: '1rem' }">
          <b-col
            :style="{
              background: `url(${require('@/assets/images/btn_bg_gr.png')}) no-repeat center /cover !important`,
            }"
            class="shadow p-3"
          >
            <b-btn
              class="w-100 text-30 text-decoration-none text-white gothic"
              variant="link"
            >
              <img
                :src="require('@/assets/images/ico_headset.png')"
                alt="상담"
              />
              전화상담 신청하기</b-btn
            >
          </b-col>
          <b-col
            :style="{
              background: `url(${require('@/assets/images/btn_bg_rd.png')}) no-repeat center /cover !important`,
            }"
            class="shadow p-3"
          >
            <b-btn
              class="w-100 text-30 text-decoration-none text-white gothic"
              variant="link"
              ><img
                :src="require('@/assets/images/ico_graph.png')"
                alt="그래프"
              />
              간편 한도조회</b-btn
            >
          </b-col>
        </b-row>
      </b-container>
    </section>
    <!-- 편한아파트론 상품안내 -->
    <section
      class="text-black border-bottom py-3"
      :style="{ background: bgGradient[0] }"
    >
      <b-container class="py-5">
        <h2 class="hana b text-25 text-center pb-3">
          <span class="mainColor">편한아파트론</span> 상품안내
        </h2>
        <b-row :style="{ gap: '1rem', marginTop: '1rem' }">
          <b-col
            class="rounded bg-white p-4"
            :style="{ border: '1px solid #cdcdcd' }"
          >
            <b-row class="align-items-center h-100">
              <h3 class="hana b mainColor2 text-25 mb-3">대출대상</h3>
              <p class="m-0 text-20">
                * 본인명의 및 배우자 공동명의 아파트 및 오피스텔 소유 고객님
                <br />
                * KB 시세 2억원 초과 <br />
                * 나이스 (나이스지키미 / 네이버 / PASS) 665점 이상 <br />
                * KCB (올크레딧 / 카카오 / 토스 / 핀다) 630점 이상
              </p>
            </b-row>
          </b-col>
          <b-col
            class="rounded bg-white p-4"
            :style="{ border: '1px solid #cdcdcd' }"
          >
            <b-row class="align-items-center h-100">
              <h3 class="hana b mainColor2 text-25 mb-3">한도 및 금리</h3>
              <p class="m-0 text-20">
                * 최저 300만원 ~ 최대 1억5천만원 <br />
                * 연 7.9~ 20% 이내 <br />
                * (연체이자율 : 약정이율 + 3%, 단 법정최고금리 연 20% 이내)
              </p>
            </b-row>
          </b-col>
        </b-row>
        <b-row :style="{ gap: '1rem', marginTop: '1rem' }">
          <b-col
            class="rounded bg-white p-4"
            :style="{ border: '1px solid #cdcdcd' }"
          >
            <b-row class="align-items-center h-100">
              <h3 class="hana b mainColor2 text-25 mb-3">기간 및 상환방법</h3>
              <p class="m-0 text-20">
                * 최저 12개월 ~ 최대 160개월
                <br />
                * 원리금균등분할상환, 만기일시상환
              </p>
            </b-row>
          </b-col>
          <b-col
            class="rounded bg-white p-4"
            :style="{ border: '1px solid #cdcdcd' }"
          >
            <b-row class="align-items-center h-100">
              <h3 class="hana b mainColor2 text-25 mb-3">이자부과시기</h3>
              <p class="m-0 text-20">* 매출후취</p>
            </b-row>
          </b-col>
        </b-row>
        <b-row :style="{ gap: '1rem', marginTop: '1rem' }">
          <b-col
            class="rounded bg-white p-4"
            :style="{ border: '1px solid #cdcdcd' }"
          >
            <b-row class="align-items-center h-100">
              <h3 class="hana b mainColor2 text-25 mb-3">대출부대비용</h3>
              <p class="m-0 text-20">* 5천만원 초과 실행시 인지세발생</p>
            </b-row>
          </b-col>
          <b-col
            class="rounded bg-white p-4"
            :style="{ border: '1px solid #cdcdcd' }"
          >
            <b-row class="align-items-center h-100">
              <h3 class="hana b mainColor2 text-25 mb-3">중도상환수수료율</h3>
              <p class="m-0 text-20">
                * 중도 2% 사용기간마다 일시 차감되는 방식으로 차등적용되는
                상품이며, 3년 경과시 중도상환수수료는 없습니다.
              </p>
            </b-row>
          </b-col>
        </b-row>
      </b-container>
    </section>
    <!-- 편한아파트론 이용방법 -->
    <section class="text-black bg-light border-bottom py-3">
      <b-container class="py-5">
        <h2 class="hana b text-25 text-center pb-3">
          <span class="mainColor">편한아파트론</span> 이용방법
        </h2>
        <b-row class="text-center mt-3" :style="{ gap: '1rem' }">
          <b-col class="shadow">
            <b-row class="text-white" :style="{ background: bgGradient[1] }">
              <span class="hana b text-22 py-2">STEP 1</span>
            </b-row>
            <b-row class="bg-white py-4">
              <h3 class="hana text-25 mainColor">대출상담 신청</h3>
              <p class="text-22 m-0">홈페이지에서 <br />대출상담 신청</p>
            </b-row>
          </b-col>
          <b-col class="shadow">
            <b-row
              class="mainBg text-white"
              :style="{ background: bgGradient[2] }"
            >
              <span class="hana b text-22 py-2">STEP 2</span>
            </b-row>
            <b-row class="bg-white py-4">
              <h3 class="hana text-25 mainColor">대출한도 및 금리확인</h3>
              <p class="text-22 m-0">상담원과의 <br />대출진행 상담</p>
            </b-row>
          </b-col>
          <b-col class="shadow">
            <b-row
              class="mainBg text-white"
              :style="{ background: bgGradient[3] }"
            >
              <span class="hana b text-22 py-2">STEP 3</span>
            </b-row>
            <b-row class="bg-white py-4">
              <h3 class="hana text-25 mainColor">서류제출 및 자서작성</h3>
              <p class="text-22 m-0">대출진행건 <br />서류제출과 자서작성</p>
            </b-row>
          </b-col>
          <b-col class="shadow">
            <b-row
              class="mainBg text-white"
              :style="{ background: bgGradient[4] }"
            >
              <span class="hana b text-22 py-2">STEP 4</span>
            </b-row>
            <b-row class="bg-white py-4">
              <h3 class="hana text-25 mainColor">서류심사 및 최종확인</h3>
              <p class="text-22 m-0">서류심사 후 <br />최종결과 통보</p>
            </b-row>
          </b-col>
          <b-col class="shadow">
            <b-row
              class="mainBg text-white"
              :style="{ background: bgGradient[5] }"
            >
              <span class="hana b text-22 py-2">STEP 5</span>
            </b-row>
            <b-row class="bg-white py-4">
              <h3 class="hana text-25 mainColor">대출승인</h3>
              <p class="text-22 m-0">신청하신 <br />대출금 입금</p>
            </b-row>
          </b-col>
        </b-row>
      </b-container>
    </section>
    <!-- 편한아파트론 Q&A -->
    <section class="text-black border-bottom py-3">
      <b-container class="py-5">
        <h2 class="hana b text-25 text-center pb-3">
          <span class="mainColor">편한아파트론</span> Q&A
        </h2>
        <b-row
          class="border rounded py-4 px-5 text-20 align-items-center text-secondary mt-4 shadow-sm"
        >
          <b-col>
            <b-row class="align-items-center">
              <b-col cols="1">
                <span
                  class="hana b mainBg text-white rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >Q</span
                >
              </b-col>
              <b-col cols="11">
                <p class="fw-900 d-inline m-0">
                  아파트담보대출과 다른 점이 무엇인가요?
                </p>
              </b-col>
            </b-row>
          </b-col>
          <b-col>
            <b-row class="align-items-center">
              <b-col cols="1">
                <span
                  class="hana b subBg text-white d-inline-block rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >A</span
                >
              </b-col>
              <b-col cols="11">
                <p class="fw-600 d-inline m-0">
                  편한아파트론은 저당설정없는 신용대출 상품으로 등기부 기재가
                  없습니다. 그러므로 등기부등본에 기록이 남지 않아서 추후 매매
                  임대시 영향이 전혀 없습니다.
                </p>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
        <b-row
          class="border rounded py-4 px-5 text-20 align-items-center text-secondary mt-4 shadow-sm"
        >
          <b-col>
            <b-row class="align-items-center">
              <b-col cols="1">
                <span
                  class="hana b mainBg text-white rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >Q</span
                >
              </b-col>
              <b-col cols="11">
                <p class="fw-900 d-inline m-0">본인명의 아파트만 취급하나요?</p>
              </b-col>
            </b-row>
          </b-col>
          <b-col>
            <b-row class="align-items-center">
              <b-col cols="1">
                <span
                  class="hana b subBg text-white d-inline-block rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >A</span
                >
              </b-col>
              <b-col cols="11">
                <p class="fw-600 d-inline m-0">
                  배우자 공동명의도 대출진행이 가능합니다. 단, 지분율 50% 이상
                  조건으로 배우자 공동소유시 취급가능합니다.
                </p>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
        <b-row
          class="border rounded py-4 px-5 text-20 align-items-center text-secondary mt-4 shadow-sm"
        >
          <b-col>
            <b-row class="align-items-center">
              <b-col cols="1">
                <span
                  class="hana b mainBg text-white rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >Q</span
                >
              </b-col>
              <b-col cols="11">
                <p class="fw-900 d-inline m-0">
                  본사 방문 없이 진행이 가능하나요?
                </p>
              </b-col>
            </b-row>
          </b-col>
          <b-col>
            <b-row class="align-items-center">
              <b-col cols="1">
                <span
                  class="hana b subBg text-white d-inline-block rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >A</span
                >
              </b-col>
              <b-col cols="11">
                <p class="fw-600 d-inline m-0">
                  무방문 당일로 대출이 진행됩니다. 공인인증서는 필수입니다.
                </p>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
        <b-row
          class="border rounded py-4 px-5 text-20 align-items-center text-secondary mt-4 shadow-sm"
        >
          <b-col>
            <b-row class="align-items-center">
              <b-col cols="1">
                <span
                  class="hana b mainBg text-white rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >Q</span
                >
              </b-col>
              <b-col cols="11">
                <p class="fw-900 d-inline m-0">
                  소득이 없고 아파트만 있는데 가능하나요?
                </p>
              </b-col>
            </b-row>
          </b-col>
          <b-col>
            <b-row class="align-items-center">
              <b-col cols="1">
                <span
                  class="hana b subBg text-white d-inline-block rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >A</span
                >
              </b-col>
              <b-col cols="11">
                <p class="fw-600 d-inline m-0">
                  무직자 전업 주부가 가능합니다.
                </p>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
        <b-row
          class="border rounded py-4 px-5 text-20 align-items-center text-secondary mt-4 shadow-sm"
        >
          <b-col>
            <b-row class="align-items-center">
              <b-col cols="1">
                <span
                  class="hana b mainBg text-white rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >Q</span
                >
              </b-col>
              <b-col cols="11">
                <p class="fw-900 d-inline m-0">
                  비거주인 경우 세입자가 있는데 동의가 있어야되나요?
                </p>
              </b-col>
            </b-row>
          </b-col>
          <b-col>
            <b-row class="align-items-center">
              <b-col cols="1">
                <span
                  class="hana b subBg text-white d-inline-block rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >A</span
                >
              </b-col>
              <b-col cols="11">
                <p class="fw-600 d-inline m-0">
                  비거주인 경우 임차인(세입자)가 있는 경우에도 대출이 가능하며
                  세입자 모르게 대출이 되는 장점이 있습니다.
                </p>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
      </b-container>
    </section>
    <GoButton />
  </main>
</template>

<script>
import GoButton from "../Layout/GoButton.vue";

export default {
  name: "Home",
  components: { GoButton },
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
    };
  },
  methods: {},
};
</script>

<style lang="scss"></style>
