<template>
  <v-container class="d-flex align-center text-center m-0" fluid>
    <div class="footer-content">
      <img class="mb-10 mt-16" src="../assets/logo.svg" />
      <hr class="mb-4" />
      <span>&#169; 2021</span>
    </div>
  </v-container>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
.footer-content {
  width: 100%;
}
.container {
  background: #d5daff;
}
span {
  font-family: Nunito;
  font-size: 18px;
  color: #000000;
}
</style>