<template>
  <b-nav
    class="position-fixed"
    :style="{
      bottom: '22rem',
      right: '3rem',
      display: 'block !important',
      zIndex: 2 
    }"
  >
    <a
      class="go-button d-flex justify-content-center align-items-center fw-900 text-20 mb-2"
      href="#inquiry" v-smooth-scroll="{ duration: 200, offset: 40 }"
    >
        대출상품
    </a>
    <a
      class="go-button d-flex justify-content-center align-items-center fw-900 text-20"
      href="#top" v-smooth-scroll="{ duration: 200, offset: 0 }"
    >
        TOP
    </a>
  </b-nav>
</template>

<script>
export default {
    name: 'GoButton',
};
</script>

<style lang="scss" scoped>
.go-button {
    width: 6rem;
    height: 3rem;
    background: #009591;
    color: #fff;
    border: 2px solid #000;
    &:hover {
      color: inherit;
    }
}
</style>