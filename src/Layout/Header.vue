<template>
  <header class="border-bottom hana" id="header">
    <b-container id="top">
      <b-row class="align-items-center justify-content-between py-3 py-md-4">
        <b-col class="" md="3" cols="2">
          <b-navbar-brand
            tag="h1"
            class="m-0 p-0 fw-900 text-25 cursor-pointer hana l"
            :style="{ color: '#008486' }"
            @click="$router.push('/').catch(() => {}), scrollTop()"
          >
            <img src="@/assets/images/logo.svg" alt="이도금융" width="40" />
            <span class="d-none d-md-inline-block ms-md-2"> 이도금융 </span>
          </b-navbar-brand>
        </b-col>
        <b-col class="text-24 text-end p-0" md="8" cols="10">
          <b-row class="align-items-center justify-content-between">
            <!-- 관리자 헤더 -->
            <template v-if="path.includes('/admin')">
              <!-- 로그인 상태 -->
              <template v-if="$store.getters.isLogin">
                <b-col class="gothic text-md-22 text-18" cols="10" md="8">
                  <b-nav
                    class="justify-content-center justify-content-md-start"
                  >
                    <b-nav-item
                      to="/admin/inquiryList"
                      :class="
                        path.includes('/admin/inquiryList') ? 'active' : ''
                      "
                      >상담신청
                      <span class="d-none d-md-inline-block"> 관리 </span>
                    </b-nav-item>
                    <b-nav-item
                      to="/admin/userList"
                      v-if="$store.getters.isSuper"
                      class="d-none d-md-inline-block"
                      :class="path.includes('/admin/user') ? 'active' : ''"
                      >계정 관리</b-nav-item
                    >
                    <b-nav-item
                      to="/admin/myAccount"
                      :class="path.includes('/admin/myAccount') ? 'active' : ''"
                      >내 정보<span class="d-none d-md-inline-block"
                        >수정</span
                      ></b-nav-item
                    >
                  </b-nav>
                </b-col>
                <b-col class="d-none d-md-inline-block" cols="" md="4">
                  <span class="mx-2 gothic text-18">
                    {{ $store.state.name }}({{ $store.state.serviceId }}) 님
                  </span>
                  <b-btn
                    @click="logout()"
                    pill
                    class="text-decoration-none"
                    variant="dark"
                  >
                    <span class="gothic"> 로그아웃 </span>
                  </b-btn>
                </b-col>
                <b-col class="d-inline-block d-md-none" cols="2">
                  <font-awesome-icon
                    @click="logout()"
                    icon="fa-solid fa-arrow-right-from-bracket"
                  />
                </b-col>
              </template>
              <!-- 로그아웃 상태 -->
              <template v-else>
                <b-col class="gothic">
                  <span class="text-20"> 관리자 전용 페이지 </span></b-col
                >
              </template>
            </template>
            <!-- 기본 헤더 -->
            <template v-else>
              <b-col class="gothic">
                <b-nav class="justify-content-center">
                  <b-nav-item
                    @click="scrollTop()"
                    to="/loanType"
                    :class="path.includes('/loanType') ? 'active' : ''"
                  >
                    대출상품
                  </b-nav-item>
                  <b-nav-item
                    @click="scrollTop()"
                    to="/inquiry"
                    :class="path.includes('/inquiry') ? 'active' : ''"
                  >
                    상담접수
                  </b-nav-item>
                </b-nav>
              </b-col>
              <b-col class="gothic d-none d-md-block">
                <span class="me-2 text-22 gothic r">상담전화</span>
                <a href="tel:1600-1481" class="mainColor text-30 align-middle"
                  >1600-1481</a
                >
              </b-col>
            </template>
          </b-row>
        </b-col>
      </b-row>
    </b-container>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      user: true,
    };
  },
  computed: {
    path() {
      return this.$route.path;
    },
  },
  methods: {
    logout() {
      this.$store.dispatch("logout");
    },
    scrollTop() {
      window.scrollTo(0, 0);
    },
  },
};
</script>

<style lang="scss" scoped>
.nav-item {
  &.active {
    .nav-link {
      color: #ed1550;
    }
  }
  .nav-link {
    color: #000;
    // &:hover,
    &:active {
      color: #000;
    }
  }
}
.logout-btn {
  background: #ffdf14;
  border: 2px solid #000;
  box-shadow: 2px 2px 0 0 #000;
  span {
    color: #000;
  }
}
</style>
