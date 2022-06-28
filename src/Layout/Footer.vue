<template>
  <footer id="footer">
    <!-- 관리자화면 -->
    <template v-if="path.includes('/admin')">
      <section class="py-5 bg-light">
        <b-container>
          <p class="m-0 opacity-50 text-center text-17">
            copyright © sitename.co.kr. All rights reserved.
          </p>
        </b-container>
      </section>
    </template>
    <!-- 유저화면 -->
    <template v-else>
      <section>
        <b-container class="py-5 gothic">
          <b-row class="align-items-center">
            <b-col>
              <img :src="require('@/assets/images/pig.png')" alt="" />
            </b-col>
            <b-col class="text-36">
              전국 어디서나! 24시간 빠른대출! <br />
              <a class="d-inline-block text-65 mainColor" href="tel:1600-1481">
                1600-1481
              </a>
            </b-col>
          </b-row>
        </b-container>
      </section>
      <section class="notice bg-light">
        <b-container class="py-5">
          <ul class="text-17">
            <li>
              <span>※</span>
              <span>
                계약을 체결하기 전에 상품 설명서와 약관을 확인하시기
                바랍니다.</span
              >
            </li>
            <li>
              <span>※</span>
              <span class="fw-900">
                상환능력에 비해 대출금이 과도할 경우 귀하의 신용등급 또는
                개인신용평점이 하락할 수 있습니다.</span
              >
            </li>
            <li>
              <span>※</span>
              <span class="fw-900">
                개인신용평점 하락 시 금융거래와 관련된 불이익이 발생할 수
                있습니다.</span
              >
            </li>
            <li>
              <span>※</span>
              <span class="fw-900">
                일정기간 원리금을 연체할 경우, 모든 원리금을 변제할 의무가
                발생할 수 있습니다.</span
              >
            </li>
            <li>
              <span>※</span>
              <span>
                대출취급이 부적정한 경우(연체금 보유, 개인신용평점 낮음) 대출이
                제한될 수 있습니다.</span
              >
            </li>
            <li>
              <span>※</span>
              <span>
                금융소비자는 해당상품에 대하여 설명을 받을 권리가 있으며, 그
                설명을 듣고 내용을 충분히 이해한 후 거래하시기 바랍니다.</span
              >
            </li>
            <li>
              <span>※</span>
              <span>
                금리인하요구권 및 대출계약 철회권에 대한 자세한 사항은
                홈페이지에서 확인하시기 바랍니다.</span
              >
            </li>
            <li>
              <span>※</span>
              <span>
                금융소비자의 개인신용평점에 따라 대출한도 및 금리가 차등
                적용됩니다.</span
              >
            </li>
            <li>
              <span>※</span
              ><span> 준법심의필 : 22-1128 (2022.05.01 ~ 2023.04.30)</span>
            </li>
            <li>
              <span>※</span>
              <span>
                여신금융협회 심의필 : 제 2022-L1h-03240호 (2022.05.01 ~
                2023.04.30)</span
              >
            </li>
          </ul>
        </b-container>
      </section>
      <section class="address py-5 opacity-50">
        <b-container>
          <b-row class="border-bottom pb-4">
            <b-col>
              <b-navbar-brand tag="h1" class="m-0 p-0 fw-900 text-25 hana cm">
                <img
                  src="@/assets/images/logo.svg"
                  alt="이도금융"
                  width="40"
                  :style="{ filter: 'grayscale(1) brightness(1.4)' }"
                />
                이도금융
              </b-navbar-brand>
            </b-col>
            <b-col class="footer-btns text-end">
              <b-button v-b-modal.check-1 variant="link text-17"
                >개인정보취급방침</b-button
              >
              <b-button v-b-modal.check-2 variant="link text-17"
                >이용동의</b-button
              >
              <b-button variant="link text-17">등록업체조회</b-button>
              <b-button variant="link text-17" to="/admin/inquiryList"
                >사이트 관리</b-button
              >
            </b-col>
          </b-row>
          <b-row class="align-items-center text-17 pt-4">
            <address class="p-0">
              사이트명: 야호캐피탈 | 상호: (주)119머니대부중개 | TEL: 1670-6520
              | 사업자번호: 131-86-39685 | 대표: 박원희<br />
              등록기관: 인천시 남동구청(생활경제과 032-453-5197) |
              대부업등록번호: 인천남동구 2021-09 | 대부중개업등록번호:
              남동구2012-41<br />
              주소: 인천광역시 남동구 예술로226번길 34, 로뎀프라자 301호(구월동)
              | 대출금리 연 20%이내(연체금리는 최대 연 20%이내)
            </address>
            <p class="mb-0 p-0">
              해당 상품은 신용 및 담보대출이며, 고객님의 개인신용평점 등
              신용도에 따라 이자율이 산출되어 적용. 대출기간
              12개월~60개월(예시:이자는 매월 약정일에 부과. 100만원을 연20%로
              12개월 동안 원리금 균등 상환 시 총 납부금액 1,111,614원) 단,
              연체대출금보유자, 불건전대출이 있는 자 등은 대출취급이 제한.
              일정기간 납부해야 할 원리금이 연체될 경우에 계약만료 기한이
              도래하기 전에 모든 원리금을 변제해야 할 의무가 발생할 수 있습니다.
              일반금융소비자는 금융판매사업자로부터 충분히 설명을 받을 권리가
              있으며, 설명 내용을 이해하신 후 계약 및 금융상품체결 전에
              금융상품설명서 및 약관을 읽어보시기 바랍니다. 채무의 조기상환 조건
              없음. 단, 담보대출은 최대4%이내 중도상환수수료 발생,
              담보권설정비용 발생, 대출금을 자동화기기로 인출시 자동화기기
              이용요금을 부담. 부대비용:채무확인서 발급비, 부동산담보대출의 경우
              국민주택채권매입비, 주소변경비용, 확인서면비용 근저당해지비용 등
              발생하며, 계약체결 후 29일 이내 상환시 대부금융사가 부담한
              등록면허세, 지방교육세반환 자동차, 부동산 담보대출 근저당 말소비용
              채무자부담 과도한 빚은 당신에게 큰 불행을 안겨줄 수 있습니다.이자
              외 별도로 중개수수료를 요구하거나 수취하는 것은 불법 입니다.
              상환능력에 비해 대출금이 과도할 경우 귀하의 신용등급 또는
              개인신용평점이 하락할 수 있고 다른금융거래가 제약 받을 수 있음
              (대출 상품에 따라 달라질 수 있습니다.)
            </p>
          </b-row>
        </b-container>
      </section>
    </template>
  </footer>
</template>

<script>
export default {
  name: "Footer",
  computed: {
    path() {
      return this.$route.path;
    },
  },
};
</script>

<style lang="scss" scoped></style>
