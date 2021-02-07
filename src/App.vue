<template>
  <div class="rashin">
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
  </div>
</template>

<script>

import Header from "./components/Header.vue";
import LeftMenu from "./components/LeftMenu.vue";
import Content from "./components/Content.vue";
import OtherMovies from "./components/OtherMovies.vue";
import PageNumbers from "./components/PageNumbers.vue";
import "./assets/scss/style.scss";

export default {
  name: "App",
  components: {
    Header,
    LeftMenu,
    Content,
    OtherMovies,
    PageNumbers,
  },
};
</script>


