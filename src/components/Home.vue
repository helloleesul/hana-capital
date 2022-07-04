<template>
  <main>
    <!-- 편한아파트론 메인-->
    <section
      class="text-black border-bottom py-3"
      :style="{
        background: `url(${require('@/assets/images/visual_bg.jpg')}) no-repeat center /cover`,
      }"
    >
      <b-container class="py-md-5 py-2">
        <h2 class="hana b text-25 text-center pb-md-3 pb-1 mainColor">
          편한아파트론
        </h2>
        <p class="text-md-50 text-30 text-center gothic lh-sm">
          쉽다! 빠르다! <br class="d-block d-md-none" />아파트소유자 신용대출
          <br />
          <span :style="{ color: bgGradient[5] }">저당 설정없이 </span>
          <span :style="{ color: bgGradient[2] }">넉넉한 한도!</span>
        </p>
        <b-row
          class="text-center align-items-end my-md-5 my-2 pb-md-0 pt-md-3 pb-3 pt-3 home-icons"
        >
          <b-col class="border-end p-0" cols="4" md="">
            <img
              :src="require('@/assets/images/img_rate.png')"
              alt="최저금리"
              class="mb-md-5 mb-2"
            />
            <p class="text-md-40 text-18 gothic r m-0 lh-sm">
              <span
                class="text-md-20 text-18 d-block gothic"
                :style="{ color: bgGradient[5] }"
              >
                최저금리
              </span>
              연 <span class="gothic">7.9%</span>
            </p>
          </b-col>
          <b-col class="border-end p-0" cols="4" md="">
            <img
              :src="require('@/assets/images/img_limit.png')"
              alt="최대한도"
              class="mb-md-5 mb-2"
            />
            <p class="text-md-40 text-18 gothic r m-0 lh-sm">
              <span
                class="text-md-20 text-18 d-block gothic"
                :style="{ color: bgGradient[5] }"
              >
                최대한도
              </span>
              <span class="gothic">1억 5,000</span>만원
            </p>
          </b-col>
          <b-col class="p-0" cols="4" md="">
            <img
              :src="require('@/assets/images/img_repay.png')"
              alt="상환기간"
              class="mb-md-5 mb-2"
            />
            <p class="text-md-40 text-18 gothic r m-0 lh-sm">
              <span
                class="text-md-20 text-18 d-block gothic"
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
            class="shadow"
          >
            <b-btn
              class="w-100 text-md-30 text-20 text-decoration-none text-white gothic p-md-4"
              variant="link"
              href="tel:1600-1481"
            >
              <img
                :src="require('@/assets/images/ico_headset.png')"
                alt="상담"
                class="d-none d-md-inline-block"
              />
              전화상담
              <span class="d-none d-md-inline-block">신청하기</span>
            </b-btn>
          </b-col>
          <b-col
            :style="{
              background: `url(${require('@/assets/images/btn_bg_rd.png')}) no-repeat center /cover !important`,
            }"
            class="shadow"
          >
            <b-btn
              class="w-100 text-md-30 text-20 text-decoration-none text-white gothic p-md-4"
              variant="link"
              ><img
                :src="require('@/assets/images/ico_graph.png')"
                alt="그래프"
                class="d-none d-md-inline-block"
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
      <b-container class="py-md-5 py-2">
        <h2 class="hana b text-25 text-center pb-md-3 pb-1">
          <span class="mainColor">편한아파트론</span> 상품안내
        </h2>
        <b-row class="gy-md-4 gy-2">
          <b-col cols="12" md="6">
            <b-row
              class="align-items-center h-100 rounded bg-white p-4"
              :style="{ border: '1px solid #cdcdcd' }"
            >
              <h3 class="hana b mainColor2 text-md-25 text-22 mb-3">
                대출대상
              </h3>
              <p class="m-0 text-md-20 text-18">
                * 본인명의 및 배우자 공동명의 아파트 및 오피스텔 소유 고객님
                <br />
                * KB 시세 2억원 초과 <br />
                * 나이스 (나이스지키미 / 네이버 / PASS) 665점 이상 <br />
                * KCB (올크레딧 / 카카오 / 토스 / 핀다) 630점 이상
              </p>
            </b-row>
          </b-col>
          <b-col cols="12" md="6">
            <b-row
              class="align-items-center h-100 rounded bg-white p-4"
              :style="{ border: '1px solid #cdcdcd' }"
            >
              <h3 class="hana b mainColor2 text-md-25 text-22 mb-3">
                한도 및 금리
              </h3>
              <p class="m-0 text-md-20 text-18">
                * 최저 300만원 ~ 최대 1억5천만원 <br />
                * 연 7.9~ 20% 이내 <br />
                * (연체이자율 : 약정이율 + 3%, 단 법정최고금리 연 20% 이내)
              </p>
            </b-row>
          </b-col>
          <b-col cols="12" md="6">
            <b-row
              class="align-items-center h-100 rounded bg-white p-4"
              :style="{ border: '1px solid #cdcdcd' }"
            >
              <h3 class="hana b mainColor2 text-md-25 text-22 mb-3">
                기간 및 상환방법
              </h3>
              <p class="m-0 text-md-20 text-18">
                * 최저 12개월 ~ 최대 160개월
                <br />
                * 원리금균등분할상환, 만기일시상환
              </p>
            </b-row>
          </b-col>
          <b-col cols="12" md="6">
            <b-row
              class="align-items-center h-100 rounded bg-white p-4"
              :style="{ border: '1px solid #cdcdcd' }"
            >
              <h3 class="hana b mainColor2 text-md-25 text-22 mb-3">
                이자부과시기
              </h3>
              <p class="m-0 text-md-20 text-18">* 매출후취</p>
            </b-row>
          </b-col>
          <b-col cols="12" md="6">
            <b-row
              class="align-items-center h-100 rounded bg-white p-4"
              :style="{ border: '1px solid #cdcdcd' }"
            >
              <h3 class="hana b mainColor2 text-md-25 text-22 mb-3">
                대출부대비용
              </h3>
              <p class="m-0 text-md-20 text-18">
                * 5천만원 초과 실행시 인지세발생
              </p>
            </b-row>
          </b-col>
          <b-col cols="12" md="6">
            <b-row
              class="align-items-center h-100 rounded bg-white p-4"
              :style="{ border: '1px solid #cdcdcd' }"
            >
              <h3 class="hana b mainColor2 text-md-25 text-22 mb-3">
                중도상환수수료율
              </h3>
              <p class="m-0 text-md-20 text-18">
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
      <b-container class="py-md-5 py-2">
        <h2 class="hana b text-25 text-center pb-md-3 pb-1">
          <span class="mainColor">편한아파트론</span> 이용방법
        </h2>
        <b-row class="text-center mt-3" :style="{ gap: '1rem' }">
          <b-col class="shadow p-0" cols="12" md="">
            <b-row class="text-white" :style="{ background: bgGradient[1] }">
              <span class="hana b text-md-22 text-20 py-md-2 py-1">STEP 1</span>
            </b-row>
            <b-row class="bg-white py-md-4 py-2">
              <h3 class="hana text-22 mainColor">대출상담 신청</h3>
              <p class="text-md-22 text-20 m-0">
                홈페이지에서 <br />대출상담 신청
              </p>
            </b-row>
          </b-col>
          <b-col class="shadow p-0" cols="12" md="">
            <b-row
              class="mainBg text-white"
              :style="{ background: bgGradient[2] }"
            >
              <span class="hana b text-md-22 text-20 py-md-2 py-1">STEP 2</span>
            </b-row>
            <b-row class="bg-white py-md-4 py-2">
              <h3 class="hana text-22 mainColor">대출한도 및 금리확인</h3>
              <p class="text-md-22 text-20 m-0">
                상담원과의 <br />대출진행 상담
              </p>
            </b-row>
          </b-col>
          <b-col class="shadow p-0" cols="12" md="">
            <b-row
              class="mainBg text-white"
              :style="{ background: bgGradient[3] }"
            >
              <span class="hana b text-md-22 text-20 py-md-2 py-1">STEP 3</span>
            </b-row>
            <b-row class="bg-white py-md-4 py-2">
              <h3 class="hana text-22 mainColor">서류제출 및 자서작성</h3>
              <p class="text-md-22 text-20 m-0">
                대출진행건 <br />서류제출과 자서작성
              </p>
            </b-row>
          </b-col>
          <b-col class="shadow p-0" cols="12" md="">
            <b-row
              class="mainBg text-white"
              :style="{ background: bgGradient[4] }"
            >
              <span class="hana b text-md-22 text-20 py-md-2 py-1">STEP 4</span>
            </b-row>
            <b-row class="bg-white py-md-4 py-2">
              <h3 class="hana text-22 mainColor">서류심사 및 최종확인</h3>
              <p class="text-md-22 text-20 m-0">
                서류심사 후 <br />최종결과 통보
              </p>
            </b-row>
          </b-col>
          <b-col class="shadow p-0" cols="12" md="">
            <b-row
              class="mainBg text-white"
              :style="{ background: bgGradient[5] }"
            >
              <span class="hana b text-md-22 text-20 py-md-2 py-1">STEP 5</span>
            </b-row>
            <b-row class="bg-white py-md-4 py-2">
              <h3 class="hana text-22 mainColor">대출승인</h3>
              <p class="text-md-22 text-20 m-0">신청하신 <br />대출금 입금</p>
            </b-row>
          </b-col>
        </b-row>
      </b-container>
    </section>
    <!-- 편한아파트론 Q&A -->
    <section class="text-black border-bottom py-3">
      <b-container class="py-md-5 py-2">
        <h2 class="hana b text-25 text-center pb-md-3 pb-1">
          <span class="mainColor">편한아파트론</span> Q&A
        </h2>
        <b-row
          class="border rounded py-4 px-md-5 px-2 text-20 align-items-center text-secondary mt-4 shadow-sm"
        >
          <b-col cols="12" md="6">
            <b-row class="align-items-md-center align-items-top mb-2 mb-md-0">
              <b-col cols="2" md="1">
                <span
                  class="hana b mainBg text-white rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >Q</span
                >
              </b-col>
              <b-col cols="10" md="11">
                <p class="fw-900 d-inline m-0 text-md-20 text-18">
                  아파트담보대출과 다른 점이 무엇인가요?
                </p>
              </b-col>
            </b-row>
          </b-col>
          <b-col cols="12" md="6">
            <b-row class="align-items-md-center align-items-top">
              <b-col cols="2" md="1">
                <span
                  class="hana b subBg text-white d-inline-block rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >A</span
                >
              </b-col>
              <b-col cols="10" md="11">
                <p class="fw-600 d-inline m-0 text-md-20 text-18">
                  편한아파트론은 저당설정없는 신용대출 상품으로 등기부 기재가
                  없습니다. 그러므로 등기부등본에 기록이 남지 않아서 추후 매매
                  임대시 영향이 전혀 없습니다.
                </p>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
        <b-row
          class="border rounded py-4 px-md-5 px-2 text-20 align-items-center text-secondary mt-4 shadow-sm"
        >
          <b-col cols="12" md="6">
            <b-row class="align-items-md-center align-items-top mb-2 mb-md-0">
              <b-col cols="2" md="1">
                <span
                  class="hana b mainBg text-white rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >Q</span
                >
              </b-col>
              <b-col cols="10" md="11">
                <p class="fw-900 d-inline m-0 text-md-20 text-18">
                  본인명의 아파트만 취급하나요?
                </p>
              </b-col>
            </b-row>
          </b-col>
          <b-col cols="12" md="6">
            <b-row class="align-items-md-center align-items-top">
              <b-col cols="2" md="1">
                <span
                  class="hana b subBg text-white d-inline-block rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >A</span
                >
              </b-col>
              <b-col cols="10" md="11">
                <p class="fw-600 d-inline m-0 text-md-20 text-18">
                  배우자 공동명의도 대출진행이 가능합니다. 단, 지분율 50% 이상
                  조건으로 배우자 공동소유시 취급가능합니다.
                </p>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
        <b-row
          class="border rounded py-4 px-md-5 px-2 text-20 align-items-center text-secondary mt-4 shadow-sm"
        >
          <b-col cols="12" md="6">
            <b-row class="align-items-md-center align-items-top mb-2 mb-md-0">
              <b-col cols="2" md="1">
                <span
                  class="hana b mainBg text-white rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >Q</span
                >
              </b-col>
              <b-col cols="10" md="11">
                <p class="fw-900 d-inline m-0 text-md-20 text-18">
                  본사 방문 없이 진행이 가능하나요?
                </p>
              </b-col>
            </b-row>
          </b-col>
          <b-col cols="12" md="6">
            <b-row class="align-items-md-center align-items-top">
              <b-col cols="2" md="1">
                <span
                  class="hana b subBg text-white d-inline-block rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >A</span
                >
              </b-col>
              <b-col cols="10" md="11">
                <p class="fw-600 d-inline m-0 text-md-20 text-18">
                  무방문 당일로 대출이 진행됩니다. 공인인증서는 필수입니다.
                </p>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
        <b-row
          class="border rounded py-4 px-md-5 px-2 text-20 align-items-center text-secondary mt-4 shadow-sm"
        >
          <b-col cols="12" md="6">
            <b-row class="align-items-md-center align-items-top mb-2 mb-md-0">
              <b-col cols="2" md="1">
                <span
                  class="hana b mainBg text-white rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >Q</span
                >
              </b-col>
              <b-col cols="10" md="11">
                <p class="fw-900 d-inline m-0 text-md-20 text-18">
                  소득이 없고 아파트만 있는데 가능하나요?
                </p>
              </b-col>
            </b-row>
          </b-col>
          <b-col cols="12" md="6">
            <b-row class="align-items-md-center align-items-top">
              <b-col cols="2" md="1">
                <span
                  class="hana b subBg text-white d-inline-block rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >A</span
                >
              </b-col>
              <b-col cols="10" md="11">
                <p class="fw-600 d-inline m-0 text-md-20 text-18">
                  무직자 전업 주부가 가능합니다.
                </p>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
        <b-row
          class="border rounded py-4 px-md-5 px-2 text-20 align-items-center text-secondary mt-4 shadow-sm"
        >
          <b-col cols="12" md="6">
            <b-row class="align-items-md-center align-items-top mb-2 mb-md-0">
              <b-col cols="2" md="1">
                <span
                  class="hana b mainBg text-white rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >Q</span
                >
              </b-col>
              <b-col cols="10" md="11">
                <p class="fw-900 d-inline m-0 text-md-20 text-18">
                  비거주인 경우 세입자가 있는데 동의가 있어야되나요?
                </p>
              </b-col>
            </b-row>
          </b-col>
          <b-col cols="12" md="6">
            <b-row class="align-items-md-center align-items-top">
              <b-col cols="2" md="1">
                <span
                  class="hana b subBg text-white d-inline-block rounded-circle d-inline-block text-center"
                  :style="{ width: '35px', height: '35px', lineHeight: '35px' }"
                  >A</span
                >
              </b-col>
              <b-col cols="10" md="11">
                <p class="fw-600 d-inline m-0 text-md-20 text-18">
                  비거주인 경우 임차인(세입자)가 있는 경우에도 대출이 가능하며
                  세입자 모르게 대출이 되는 장점이 있습니다.
                </p>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
      </b-container>
    </section>
  </main>
</template>

<script>
export default {
  name: "Home",
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
