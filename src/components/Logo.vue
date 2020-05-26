<template>
  <div class="box-logo">
    <img class="logo" alt="Vue logo" src="../assets/logo.png" />
    <img class="neuf" src="../assets/9.png" alt="Symbole" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class Logo extends Vue {}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.box-logo {
  display: block;
  margin: auto !important;
}
.logo {
  width: 600px;
  height: 280px;
}
.neuf {
  position: relative;
  top: -150px;
  left: -120px;
  right: 0;
  width: 180px;
  height: 180px;
  margin: -90px 0 0 -90px !important;
  -webkit-animation: spin 60s linear infinite;
  -moz-animation: spin 60s linear infinite;
  animation: spin 60s linear infinite;
}
@-moz-keyframes spin {
  100% {
    -moz-transform: rotate(360deg);
  }
}
@-webkit-keyframes spin {
  100% {
    -webkit-transform: rotate(360deg);
  }
}
@keyframes spin {
  100% {
    -webkit-transform: rotate(360deg);
    transform: rotate(360deg);
  }
}
</style>
