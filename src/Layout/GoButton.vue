<template>
  <b-nav
    class="position-fixed"
    :style="{
      bottom: '26rem',
      right: '3rem',
      display: 'block !important',
      zIndex: 2,
    }"
  >
    <a
      class="go-button d-flex justify-content-center align-items-center fw-900 text-20"
      href="#loanItems"
      v-smooth-scroll="{ duration: 200, offset: 40 }"
      :style="{ zIndex: 1 }"
    >
      <span>대출상품</span>
    </a>
    <a
      class="go-button d-flex justify-content-center align-items-center fw-900 text-20 position-relative top"
      href="#top"
      v-smooth-scroll="{ duration: 200, offset: 0 }"
      :style="{ zIndex: -1 }"
    >
      <font-awesome-icon
        icon="angle-up"
        class="position-absolute"
        :style="{ top: '.5rem' }"
      />
      <span class="mt-3">TOP</span>
    </a>
  </b-nav>
</template>

<script>
export default {
  name: "GoButton",
};
</script>

<style lang="scss" scoped></style>
