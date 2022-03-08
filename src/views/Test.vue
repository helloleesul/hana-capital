<template>
  <b-container class="my-5 w-50">
    <b-row class="justify-content-center">
      <b-col class="col-5">
        <b-input placeholder="공동소유자명" v-model="inputName"></b-input>
      </b-col>
      <b-col class="col-3">
        <b-form-select v-model="inputSelected" class="w-100">
          <template #first>
            <b-form-select-option :value="null" disabled
              >관계</b-form-select-option
            >
          </template>
          <b-form-select-option value="A">Option A</b-form-select-option>
          <b-form-select-option value="B">Option B</b-form-select-option>
          <b-form-select-option value="C">Option C</b-form-select-option>
          <b-form-select-option value="D">Option D</b-form-select-option>
        </b-form-select>
      </b-col>
      <b-col class="col-1">
        <b-btn class="w-100" @click="add()">+</b-btn>
      </b-col>
    </b-row>
    <b-row class="justify-content-center">
      <b-col class="col-5">
        공동소유자명: {{ inputName ? inputName : "-" }}
      </b-col>
      <b-col class="col-3">
        관계: {{ inputSelected ? inputSelected : "-" }}
      </b-col>
    </b-row>
    <b-row class="justify-content-center">
      <ul>
        <li v-for="item in list" :key="item.id">{{ item }}</li>
      </ul>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: "Test",
  data() {
    return {
      inputName: null,
      inputSelected: null,
      list: [
        {
          name: null,
          selected: null,
        },
      ],
    };
  },
  methods: {
    add() {
      this.list = this.inputName;
      this.list = this.inputSelected;
    },
  },
};
</script>

<style></style>
