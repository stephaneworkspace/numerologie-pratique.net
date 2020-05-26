<template>
  <center>
    <section class="input-password">
      <b-field label="Mot de passe">
        <b-input type="password" value="iwantmytreasure" password-reveal>
        </b-input>
      </b-field>
    </section>
  </center>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class MotDePasse extends Vue {}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.input-password {
  border-radius: 10px;
  justify-content: center;
  width: 200px;
}
</style>
