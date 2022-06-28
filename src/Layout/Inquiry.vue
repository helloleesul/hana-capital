<template>
  <main>
    <!-- 타이틀-->
    <section
      class="text-black py-3"
      :style="{
        background: `url(${require('@/assets/images/visual_bg.jpg')}) no-repeat center /cover`,
      }"
    >
      <b-container class="py-5">
        <h2 class="gothic text-50 text-center pb-3 mainColor">대출상담 신청</h2>
        <p class="text-40 text-center gothic">
          연락처를 남겨주시면 전문상담원이 연락드립니다.
          <span class="text-20 opacity-50 d-block">
            <font-awesome-icon icon="fa-solid fa-asterisk" /> 상담만으로는
            신용조회 기록이 절대 남지 않습니다.
          </span>
        </p>
      </b-container>
    </section>
    <!-- 상담신청 -->
    <section id="inquiry" class="py-5 border-bottom">
      <b-container>
        <InquiryItem />
      </b-container>
    </section>
  </main>
</template>

<script>
import InquiryItem from "../components/InquiryItem.vue";
export default {
  name: "Inquiry",
  components: { InquiryItem },
};
</script>

<style lang="scss"></style>
