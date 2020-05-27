<template>
  <center>
    <section class="input-password">
      <div class="columns" v-if="!swAuth">
        <div class="column">
          <b-field label="Mot de passe">
            <b-input
              type="password"
              value=""
              v-model="password"
              @input="onChangePassword"
              password-reveal
            >
            </b-input>
          </b-field>
        </div>
      </div>
      <div class="columns" v-if="swAuth">
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
import { Component, Prop, Vue } from "vue-property-decorator";
const axios = require("axios").default;

@Component
export default class MotDePasse extends Vue {
  @Prop() private api!: string;
  public password = "";
  public swAuth = false;

  public onChangePassword() {
    this.getPassword();
  }

  public getPassword(): void {
    const config = {
      "Content-Type": "application/x-www-form-urlencoded"
    };
    axios.get(`${this.api}password/${this.password}`, config).then(res => {
      this.swAuth = res.data.sw_valid;
    });
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.input-password {
  margin: 0px 20px 20px;
  border-radius: 10px;
  justify-content: center;
}
</style>
