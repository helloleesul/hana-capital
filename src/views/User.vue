<template>
  <div id="user-page">
    <Header />
    <router-view />
    <Footer />
    <GoButton />
    <Modal />
  </div>
</template>

<script>
import Footer from "../Layout/Footer.vue";
import Header from "../Layout/Header.vue";
import GoButton from "../Layout/GoButton.vue";
import Modal from "../Layout/Modal.vue";

export default {
  name: "User",
  components: { Header, Footer, GoButton, Modal },
};
</script>

<style lang="scss" scoped></style>
