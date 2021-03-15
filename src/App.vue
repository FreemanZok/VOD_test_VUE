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
      {{clone()}}
    </div>


  </div>
</template>

<script>
import Header from "./components/Header.vue";
import LeftMenu from "./components/LeftMenu.vue";
import Content from "./components/Content.vue";
import OtherMovies from "./components/OtherMovies.vue";
import PageNumbers from "./components/PageNumbers.vue";
import my_mixin from "./mixins.js";

import "./assets/scss/style.scss";

export default {
  name: "App",
  mixins: [my_mixin],
  components: {
    Header,
    LeftMenu,
    Content,
    OtherMovies,
    PageNumbers,

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
