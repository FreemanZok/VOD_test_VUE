<template>
  <div id="app" class="rashin">
    <Header />
    <div class="container clearfix">
      <LeftMenu />

      <div class="others">
        <Content />
        <div class="featured">FEATURED ARTICLES</div>
        <OtherMovies />
        <PageNumbers />
      </div>
    </div>

    <div>
      <offline @detected-condition="handleConnectivityChange"> </offline>

    <div v-bind:class="[online ? 'on-line' : 'off-line']">
      <h1 v-if="online">I'm OnLine :)</h1>
      <h1 v-else>Ooh, OffLine... :(</h1>
    </div>
    </div>

  </div>
</template>

<script>
import Header from "./components/Header.vue";
import LeftMenu from "./components/LeftMenu.vue";
import Content from "./components/Content.vue";
import OtherMovies from "./components/OtherMovies.vue";
import PageNumbers from "./components/PageNumbers.vue";

import offline from "v-offline";
import "./assets/scss/style.scss";

export default {
  name: "App",
  components: {
    Header,
    LeftMenu,
    Content,
    OtherMovies,
    PageNumbers,
    offline,

  },
  data() {
    return {
      online: "",
      offline: "",
    };
  },
  methods: {
    handleConnectivityChange(status) {
      console.log(status);
      if (status) {
        this.online = true;
      } else {
        this.offline = true;
      }
    },
  },
};
</script>

<style>
.on-line{
  background: rgb(65, 225, 172);
  text-align: center;
  color: beige;
  padding: 60px;
}
.off-line{
  background: rgb(255, 160, 195);
  text-align: center;
  color: beige;
  padding: 60px;

}
</style>
