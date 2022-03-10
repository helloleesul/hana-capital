<template>
  <b-nav
    class="position-fixed"
    :style="{
      bottom: '3rem',
      right: '3rem',
      display: 'block !important',
    }"
  >
    <a
      class="go-button d-block justify-content-center text-center align-items-center fw-900 text-20 call"
      href="#"
    >
      <font-awesome-icon icon="phone" />
      <span class="d-block">전화상담</span>
    </a>
    <a
      class="go-button d-block justify-content-center text-center align-items-center fw-900 text-20 kakao"
      href="#"
    >
      <font-awesome-icon icon="comment" />
      <span class="d-block">카톡상담</span>
    </a>
    <a
      class="go-button d-block justify-content-center text-center align-items-center fw-900 text-20 inquiry"
      href="#inquiry"
      v-smooth-scroll="{ duration: 200, offset: -200 }"
      :style="{ zIndex: 1 }"
    >
      <font-awesome-icon icon="paper-plane" />
      <span class="d-block">간편신청</span>
    </a>
    <a
      class="go-button d-block justify-content-center text-center align-items-center fw-900 text-20 top"
      href="#top"
      v-smooth-scroll="{ duration: 200, offset: 0 }"
      :style="{ zIndex: -1 }"
    >
      <font-awesome-icon icon="angle-up" />
      <span class="d-block">TOP</span>
    </a>
  </b-nav>
</template>

<script>
export default {
  name: "GoButton",
};
</script>

<style lang="scss" scoped></style>
