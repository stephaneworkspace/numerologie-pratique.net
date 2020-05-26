<template>
  <div class="home">
    <Logo />
    <center>
      <MotDePasse class="box" />
    </center>
  </div>
</template>

<script>
// @ is an alias to /src
import Logo from "@/components/Logo.vue";
import MotDePasse from "@/components/MotDePasse.vue";

export default {
  name: "Home",
  components: {
    Logo,
    MotDePasse
  }
};
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.home {
  margin: 20px;
}
.box {
  border: 4px solid #ffffff;
  padding: 60px 0;
  /*text-align: center;*/
  width: 584px;
  -webkit-border-radius: 8px;
  -moz-border-radius: 8px;
  border-radius: 8px;
  -webkit-box-shadow: #666 0px 2px 3px;
  -moz-box-shadow: #666 0px 2px 3px;
  box-shadow: #666 0px 2px 3px;
  background: #ffffff;
  background: -webkit-gradient(
    linear,
    0 0,
    0 bottom,
    from(#ffffff),
    to(#000000)
  );
  background: -webkit-linear-gradient(#ffffff, #000000);
  background: -moz-linear-gradient(#ffffff, #000000);
  background: -ms-linear-gradient(#ffffff, #000000);
  background: -o-linear-gradient(#ffffff, #000000);
  background: linear-gradient(#ffffff, #000000);
  -pie-background: linear-gradient(#ffffff, #000000);
  behavior: url(/pie/PIE.htc);
  justify-contents: center;
}
</style>
