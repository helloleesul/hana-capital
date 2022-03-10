<template>
  <main>
    <section class="border-bottom main-slide">
      <b-container>
        <carousel
          :per-page="1"
          :speed="1000"
          centerMode
          :paginationSize="150"
          paginationPosition="bottom-overlay"
        >
          <slide>
            <a
              class="go-button d-block w-100 h-100 justify-content-center text-center align-items-center fw-900 text-20 top"
              href="#item-1"
              v-smooth-scroll="{ duration: 200, offset: 0 }"
              :style="{ zIndex: -1 }"
            >
              <span class="d-block">item1</span>
            </a></slide
          >
          <slide>
            <a
              class="go-button d-block w-100 h-100 justify-content-center text-center align-items-center fw-900 text-20 top"
              href="#item-2"
              v-smooth-scroll="{ duration: 200, offset: 0 }"
              :style="{ zIndex: -1 }"
            >
              <span class="d-block">item2</span>
            </a></slide
          >
          <slide>
            <a
              class="go-button d-block w-100 h-100 justify-content-center text-center align-items-center fw-900 text-20 top"
              href="#item-3"
              v-smooth-scroll="{ duration: 200, offset: 0 }"
              :style="{ zIndex: -1 }"
            >
              <span class="d-block">item3</span>
            </a></slide
          >
          <slide>
            <a
              class="go-button d-block w-100 h-100 justify-content-center text-center align-items-center fw-900 text-20 top"
              href="#item-4"
              v-smooth-scroll="{ duration: 200, offset: 0 }"
              :style="{ zIndex: -1 }"
            >
              <span class="d-block">item4</span>
            </a></slide
          >
        </carousel>
      </b-container>
    </section>
    <section class="border-bottom" id="item-1">
      <b-container>
        <b-row class="text-center align-items-center">
          <h2 class="hana font-italic text-50">item1</h2>
          <p class="fw-900 text-50 mb-5">아파트최고한도(후순위)</p>
          <span class="text-24">전국 모든 아파트소유자면 누구나가능</span>
        </b-row>
      </b-container>
    </section>
    <section class="border-bottom" id="item-2">
      <b-container>
        <b-row class="text-center align-items-center">
          <h2 class="hana font-italic text-50">item2</h2>
          <p class="fw-900 text-50 mb-5">아파트최고한도(후순위)</p>
          <span class="text-24">전국 모든 아파트소유자면 누구나가능</span>
        </b-row>
      </b-container>
    </section>
    <section class="border-bottom" id="item-3">
      <b-container>
        <b-row class="text-center align-items-center">
          <h2 class="hana font-italic text-50">item3</h2>
          <p class="fw-900 text-50 mb-5">아파트최고한도(후순위)</p>
          <span class="text-24">전국 모든 아파트소유자면 누구나가능</span>
        </b-row>
      </b-container>
    </section>
    <section class="border-bottom" id="item-4">
      <b-container>
        <b-row class="text-center align-items-center">
          <h2 class="hana font-italic text-50">item4</h2>
          <p class="fw-900 text-50 mb-5">아파트최고한도(후순위)</p>
          <span class="text-24">전국 모든 아파트소유자면 누구나가능</span>
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
        class="p-0 bg-black text-white py-5"
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

    <Modal :loanItem="loanItem" />
    <GoButton />
  </main>
</template>

<script>
import GoButton from "../Layout/GoButton.vue";
import Modal from "../Layout/Modal.vue";
import Inquiry from "../Layout/Inquiry.vue";

export default {
  name: "Home",
  components: { GoButton, Inquiry, Modal },
  data() {
    return {
      loanItem: null,
      loanItems: [
        { name: "아파트담보대출", color: "#35A67D", icon: "building" },
        { name: "공동명의지분대출", color: "#35A67D", icon: "hotel" },
        { name: "무설정아파트", color: "#35A67D", icon: "campground" },
        { name: "빌라/단독주택", color: "#35A67D", icon: "house-user" },
        { name: "전/월세 보증금", color: "#35A67D", icon: "warehouse" },
        { name: "기타부동산", color: "#35A67D", icon: "industry" },
        { name: "경매취하/압류/가압류", color: "#35A67D", icon: "store-slash" },
        { name: "자동차담보", color: "#35A67D", icon: "car" },
        { name: "직장인대출", color: "#526BAA", icon: "briefcase" },
        { name: "사업자대출", color: "#526BAA", icon: "hand-holding-usd" },
        { name: "저금리대환", color: "#526BAA", icon: "coins" },
        {
          name: "저신용자희망대출",
          color: "#526BAA",
          icon: "file-invoice-dollar",
        },
      ],
      steps: [
        {
          title: "대출상담 신청하기",
          content:
            "대출상품을 클릭 후 내용을 기입하시고 대출신청완료 버튼을 눌러주세요.",
        },
        {
          title: "담당 상담원과 통화",
          content:
            "신청하신 연락처로 담당 상담원이 대출상품 및 필요한 서류들을 안내해드립니다.",
        },
        {
          title: "구비서류 준비",
          content: "담당 상담원이 말씀드린 서류를 안내한 FAX번호로 보내주세요.",
        },
        {
          title: "대출승인",
          content:
            "대출심사완료 후 고객님이 기재하신 연락처로 대출승인금액을 통보해드립니다.",
        },
        {
          title: "대출금 송금",
          content: "대출 승인 완료 후 고객님의 온라인 계좌로 송금해드립니다.",
        },
      ],
      table: [
        { th: "대출대상", td: "전국 아파트소유자 및 담보제공가능자" },
        { th: "대출한도", td: "감정가의 100%(최대 20억)" },
        { th: "대출기간", td: "최장 30년" },
        { th: "대출금리", td: "연 5% ~ 최대 연 20%이내" },
        { th: "상환방법", td: "원리금균등분할상환, 만기일시상환" },
      ],
    };
  },
  methods: {
    modalShow(item) {
      this.loanItem = item;
      this.$bvModal.show("loanItem");
    },
  },
};
</script>

<style lang="scss" scoped>
.loanItem {
  position: absolute;
  left: 1rem;
  top: 1rem;
}
.loanItem-icon {
  position: absolute;
  right: 1rem;
  bottom: 1rem;
  opacity: 0.5;
}
table {
  width: 100%;
  border-right: 1px solid #ddd;
  border-top: 1px solid #ddd;
  box-shadow: 10px 10px 10px #eee;
  th,
  td {
    padding: 30px;
    text-align: center;
    font-size: 18px;
    border-left: 1px solid #ddd;
    border-bottom: 1px solid #ddd;
  }
  th {
    background: #f4f4f4;
    font-weight: 800;
  }
}
</style>
