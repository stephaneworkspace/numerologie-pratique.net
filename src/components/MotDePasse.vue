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
            <b-input placeholder="Nom(s) et prénom(s)" v-model="name"></b-input>
          </b-field>
        </div>
        <div class="column">
          <b-field label="Date de naissance">
            <b-datepicker
              placeholder="Date de naissance"
              icon="calendar-today"
              position="is-top-left"
              v-model="ddmmyyyy"
            >
            </b-datepicker>
          </b-field>
        </div>
        <br />
      </div>
      <div class="container is-fluid" v-if="swAuth">
        <div class="notification is-primary">
          <b-button type="is-primary" @click="modalOpen"
            >Générer thème</b-button
          >
        </div>
      </div>
    </section>
    <b-modal :active.sync="isCardModalActive" :width="640" scroll="keep">
      <div class="card">
        <!--<div class="card-image">
          <figure class="image is-4by3">
            <img src="/static/img/placeholder-1280x960.png" alt="Image" />
          </figure>
        </div>-->
        <div class="card-content">
          <div class="media">
            <!--<div class="media-left">
              <figure class="image is-48x48">
                <img src="/static/img/placeholder-1280x960.png" alt="Image" />
              </figure>
            </div>-->
            <div class="media-content">
              <!--<p class="title is-4">John Smith</p>
              <p class="subtitle is-6">@johnsmith</p>-->
            </div>
          </div>

          <div class="content">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus
            nec iaculis mauris. <a>@bulmaio</a>. <a>#css</a> <a>#responsive</a>
            <br />
            <small>11:09 PM - 1 Jan 2016</small>
          </div>
        </div>
      </div>
    </b-modal>
  </center>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
const axios = require("axios").default;

@Component
export default class MotDePasse extends Vue {
  @Prop() private api!: string;
  public password = "";
  public name = "";
  public ddmmyyyy = new Date();
  public chart = "";
  public swAuth = false;
  public isCardModalActive = false;

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

  public modalOpen(): void {
    const config = {
      "Content-Type": "application/x-www-form-urlencoded"
    };
    const year = this.ddmmyyyy.getFullYear();
    const month = this.ddmmyyyy.getMonth();
    const day = this.ddmmyyyy.getDay();

    axios
      .get(
        `${this.api}chart/${this.password}/${this.name}/${this.password}/${day}/${month}/${year}`,
        config
      )
      .then(res => {
        this.isCardModalActive = true;
        this.chart = res.data;
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
