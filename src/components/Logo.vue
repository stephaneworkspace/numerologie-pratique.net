<template>
  <img class="logo" alt="Vue logo" src="../assets/logo.png" />
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class Logo extends Vue {}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.logo {
  width: 600px;
  height: 280px;
}
</style>
