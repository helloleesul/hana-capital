<template>
  <b-row class="m-auto w-50 text-md-20">
    <validation-observer ref="observer" v-slot="{ handleSubmit }">
      <b-form @submit.prevent="handleSubmit(submit)">
        <validation-provider
          name="이름"
          :rules="{ required: true, min: 1 }"
          v-slot="validationContext"
        >
          <b-form-group
            id="name-input-group"
            label="이름"
            label-for="name-input"
            class="mb-3"
          >
            <b-form-input
              id="name-input"
              name="name-input"
              v-model="input.name"
              placeholder="이름을 입력하세요."
              :state="getValidationState(validationContext)"
              aria-describedby="name-input-feedback"
              class="text-18"
            ></b-form-input>
            <b-form-invalid-feedback id="name-input-feedback">{{
              validationContext.errors[0]
            }}</b-form-invalid-feedback>
          </b-form-group>
        </validation-provider>
        <validation-provider
          name="연락처"
          :rules="{ required: true, integer: true, min: 9, max: 11 }"
          v-slot="validationContext"
        >
          <b-form-group
            id="tel-input-group"
            label="연락처"
            label-for="tel-input"
            class="mb-3"
          >
            <b-form-input
              id="tel-input"
              name="tel-input"
              v-model="input.phone"
              type="tel"
              placeholder="-없이 입력하세요."
              maxlength="11"
              :state="getValidationState(validationContext)"
              aria-describedby="tel-input-feedback"
              class="text-18"
            ></b-form-input>
            <b-form-invalid-feedback id="tel-input-feedback">{{
              validationContext.errors[0]
            }}</b-form-invalid-feedback>
          </b-form-group>
        </validation-provider>
        <validation-provider
          name="대출금액"
          :rules="{ required: true, integer: true }"
          v-slot="validationContext"
        >
          <b-form-group
            id="contents-input-group"
            label="대출금액"
            label-for="contents-input"
            class="mb-3"
          >
            <b-form-input
              :style="{ width: '85%' }"
              class="d-inline-block text-18"
              id="contents-input"
              name="contents-input"
              v-model="input.content"
              placeholder="대출금액을 입력하세요."
              :state="getValidationState(validationContext)"
              aria-describedby="contents-input-feedback"
            ></b-form-input>
            <span class="d-inline-block text-end" :style="{ width: '15%' }"
              >만원</span
            >
            <b-form-invalid-feedback id="contents-input-feedback">{{
              validationContext.errors[0]
            }}</b-form-invalid-feedback>
          </b-form-group>
        </validation-provider>
        <validation-provider
          name="개인정보취급방침이용동의"
          :rules="{ required: true }"
          v-slot="validationContext"
        >
          <b-form-checkbox-group
            :state="getValidationState(validationContext)"
            v-model="check"
            id="check-input"
          >
            <b-form-checkbox value="개인정보취급방침이용동의">
              <span class="px-2 fw-900 text-18">개인정보취급방침이용동의</span>
              <b-btn
                v-b-modal.check-1
                variant="link"
                class="text-decoration-none p-0 align-middle"
                :style="{ color: 'inherit' }"
              >
                <span>[자세히보기]</span>
              </b-btn>
            </b-form-checkbox>
            <b-form-invalid-feedback
              id="check-input-feedback"
              :class="{ hide: checkHide }"
              >{{ validationContext.errors[0] }}</b-form-invalid-feedback
            >
          </b-form-checkbox-group>
        </validation-provider>
        <b-row
          :style="{
            background: `url(${require('@/assets/images/btn_bg_rd.png')}) no-repeat center /cover !important`,
          }"
          class="shadow mt-4"
        >
          <b-btn
            type="submit"
            class="w-100 text-md-30 text-22 text-decoration-none text-white gothic p-md-4"
            variant="link"
            ><img
              :src="require('@/assets/images/ico_headset.png')"
              alt="상담"
              class="d-none d-md-inline-block"
            />
            간편상담 신청하기</b-btn
          >
        </b-row>
      </b-form>
    </validation-observer>
  </b-row>
</template>

<script>
export default {
  name: "InquiryItem",
  data() {
    return {
      input: {
        name: null,
        phone: null,
        content: null,
      },
      check: [],
      checkHide: false,
    };
  },
  methods: {
    async submit() {
      const { data } = await this.$axios.post("/api/v1/inquiry", this.input);
      console.log(data);
      // console.log(this.input)

      if (data.code === "0000") {
        this.$bvModal
          .msgBoxOk(
            "상담신청이 완료되었습니다. 빠른 시일 내에 연락드리겠습니다.",
            {
              title: "상담신청 완료",
              size: "sm",
              buttonSize: "sm",
              okVariant: "success",
              centered: true,
              okTitle: "확인",
              footerClass: "p-2",
            }
          )
          .then(() => {
            // console.log(value)
            Object.assign(this.$data, this.$options.data());
            this.$refs.observer.reset();
            this.checkHide = true;
          });
      }
    },
    getValidationState({ dirty, validated, valid = null }) {
      return dirty || validated ? valid : null;
    },
  },
};
</script>

<style lang="scss">
#check-input-feedback {
  display: block !important;
  margin: 0 !important;
  &.hide {
    display: none !important;
  }
}
#contents-input {
  height: 38px;
}
.form-group {
  display: flex;
  label {
    width: 40%;
    + div {
      width: 60%;
    }
  }
}
</style>
