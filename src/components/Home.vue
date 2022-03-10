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
              class="d-block w-100 h-100 bg-black"
              href="#item-1"
              v-smooth-scroll="{ duration: 200, offset: 0 }"
            >
              <span class="text-white">item1</span>
            </a></slide
          >
          <slide>
            <a
              class="d-block w-100 h-100 bg-black"
              href="#item-2"
              v-smooth-scroll="{ duration: 200, offset: 0 }"
            >
              <span class="text-white">item2</span>
            </a></slide
          >
          <slide>
            <a
              class="d-block w-100 h-100 bg-black"
              href="#item-3"
              v-smooth-scroll="{ duration: 200, offset: 0 }"
            >
              <span class="text-white">item3</span>
            </a></slide
          >
          <slide>
            <a
              class="d-block w-100 h-100 bg-black"
              href="#item-4"
              v-smooth-scroll="{ duration: 200, offset: 0 }"
            >
              <span class="text-white">item4</span>
            </a></slide
          >
        </carousel>
      </b-container>
    </section>
    <section
      class="border-bottom"
      v-for="item in items"
      :id="item.id"
      :key="item.id"
    >
      <b-container>
        <b-row class="text-center align-items-center">
          <h2 class="hana font-italic text-50">{{ item.name }}</h2>
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
    <GoButton />
  </main>
</template>

<script>
import GoButton from "../Layout/GoButton.vue";
import Inquiry from "../Layout/Inquiry.vue";

export default {
  name: "Home",
  components: { GoButton, Inquiry },
  data() {
    return {
      items: [
        { id: "item-1", name: "햇살론" },
        { id: "item-2", name: "사잇돌" },
        { id: "item-3", name: "하나드림론" },
        { id: "item-4", name: "하나슈퍼드림론" },
      ],
    };
  },
  methods: {},
};
</script>

<style lang="scss" scoped></style>
