<template>
  <b-container class="my-5 w-50">
    <b-row class="justify-content-center">
      <b-col class="col-5">
        <b-input placeholder="공동소유자명" v-model="input.name"></b-input>
      </b-col>
      <b-col class="col-3">
        <b-form-select v-model="input.selected" class="w-100">
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
        <b-btn class="w-100" @click="addBtn()">+</b-btn>
      </b-col>
    </b-row>
    <b-row class="justify-content-center mt-3">
      <b-col class="col-5">
        공동소유자명: {{ input.name ? input.name : "-" }}
      </b-col>
      <b-col class="col-3">
        관계: {{ input.selected ? input.selected : "-" }}
      </b-col>
    </b-row>
    <b-row class="justify-content-center mt-5">
      <ul>
        <li v-for="(item, i) in list" :key="item.name">
          <b-row class="justify-content-center">
            <b-col class="col-5">
              <p v-if="!item.edit">
                {{ item.name }}
              </p>
              <b-input v-else v-model="item.name"></b-input>
            </b-col>
            <b-col class="col-3">
              <p v-if="!item.edit">
                {{ item.selected }}
              </p>
              <b-form-select v-else v-model="item.selected" class="w-100">
                <b-form-select-option value="A">Option A</b-form-select-option>
                <b-form-select-option value="B">Option B</b-form-select-option>
                <b-form-select-option value="C">Option C</b-form-select-option>
                <b-form-select-option value="D">Option D</b-form-select-option>
              </b-form-select>
            </b-col>
          </b-row>
          <b-btn @click="editBtn(item)">수정</b-btn>
          <b-btn @click="delBtn(i)">삭제</b-btn>
          {{ item.edit }}
        </li>
      </ul>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: "Test",
  data() {
    return {
      input: {
        name: null,
        selected: null,
      },
      list: [],
    };
  },
  methods: {
    addBtn() {
      if (this.input.name != null && this.input.selected != null) {
        this.list.push({
          name: this.input.name,
          selected: this.input.selected,
          edit: false,
        });
        this.input.name = null;
        this.input.selected = null;
      } else {
        alert("모두 입력하세여");
      }
    },
    editBtn(item) {
      item.edit = !item.edit;
    },
    delBtn(i) {
      this.list.splice(i, 1);
    },
  },
};
</script>

<style></style>
