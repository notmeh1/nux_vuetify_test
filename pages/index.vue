<template>
  <div>
    <v-img :src="bgImg" class="bgImg" height="100vh"> </v-img>
    <h1 class="bgText">Bienvenidos</h1>
  </div>
</template>

<script>
export default {
  data: () => ({
    bgImg:
      'https://assets.tonica.la/__export/1593033191339/sites/debate/img/2020/06/24/rick-and-morty-portada.jpg_759710130.jpg',
  }),
}
</script>

<style>
@font-face {
  font-family: 'GetSchwifty';
  src: url('../static/fonts/get_schwifty.ttf');
}
.container {
  padding: 0;
}
.bgImg {
  filter: blur(5px);
  height: 100%;
}
.bgText {
  color: #000000;
  font-size: 45px;
  font-family: 'GetSchwifty';
  position: absolute;
  transform: translate(-50%, -50%);
  top: 50%;
  left: 50%;
  border: 2px solid #000000;
  padding: 1em;
}
</style>
