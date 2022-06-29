<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
export default {
  name: "App",
  mounted() {
    document.title = "이도금융 캐피탈";
  },
};
</script>

<style></style>
