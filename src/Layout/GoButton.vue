<template>
  <!-- <b-nav
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
  </b-nav> -->
  <div>
    <b-btn
      class="scrollTop-btn d-none d-md-block"
      @click="scrollTop()"
      variant="link"
    >
      <font-awesome-icon icon="angles-up" class="fa-2x" />
    </b-btn>
    <div class="d-block d-md-none">
      <b-btn class="scrollTop-btn mobile" @click="scrollTop()" variant="link">
        <font-awesome-icon icon="angles-up" class="fa-2x" />
      </b-btn>
      <b-row
        class="position-fixed w-100"
        :style="{
          bottom: 0,
        }"
      >
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
            <font-awesome-icon icon="phone" class="" />
            1600-1481</b-btn
          >
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
            to="/inquiry"
          >
            상담접수</b-btn
          >
        </b-col>
      </b-row>
    </div>
  </div>
</template>

<script>
export default {
  name: "GoButton",
  methods: {
    scrollTop() {
      window.scrollTo(0, 0);
    },
  },
};
</script>

<style lang="scss" scoped></style>
