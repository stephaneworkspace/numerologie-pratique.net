<template>
  <center>
    <section class="input-password">
      <div class="columns">
        <div class="column">
          <b-field label="Mot de passe">
            <b-input type="password" value="iwantmytreasure" password-reveal>
            </b-input>
          </b-field>
        </div>
      </div>
      <div class="columns">
        <div class="column">
          <b-field label="Nom(s)/Prenom(s)">
            <b-input type="nom" placeholder="Nom(s) et prénom(s)"> </b-input>
          </b-field>
        </div>
        <div class="column">
          <b-field label="Date de naissance">
            <b-datepicker
              placeholder="Date de naissance"
              icon="calendar-today"
              position="is-top-left"
            >
            </b-datepicker>
          </b-field>
        </div>
      </div>
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
  margin: 0px 20px 20px;
  border-radius: 10px;
  justify-content: center;
}
</style>
