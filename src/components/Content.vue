<template>
  <div class="main-content">
    <div class="landscape-box">
      <div class="landscape-img-wrapper">
        <img id="landscape" class="inner-img" :src="landscape" alt="salam" />
      </div>
      <div class="movie_info">
        <div class="movie_title">{{ title_landsacape }}</div>
        <div class="movie_discription">{{ summary_landsacape }}</div>
      </div>
    </div>

    <div class="center-box clearfix">
      <div
        class="center-img-box"
        v-for="(item, i) in 4"
        v-bind:key="item.id"   
      >
        <div class="center-img-wrapper">
          <img class="inner-img img-center" :src="four_movies.portrait[i]" />
        </div>
        <div class="movie_info">
          <div class="movie_title-center">{{ four_movies.title[i] }}</div>
          <div class="movie_discription-center">{{ four_movies.summary[i]}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Content",
  data: function () {
    return {
      ali: [],
      index: 0,
      title_landsacape: "",
      summary_landsacape: "",
      landscape: "",

      four_movies: {
          title: [],
          summary: [],
          image: [],
          portrait: [],
      },
    };
  },
  mounted: function () {
    fetch("http://apitest.tek-nic.com/movie/FirstPage", {
      method: "get",
    })
      .then((response) => {
        var hi = response.json()
        return hi
      })
      .then((info) => {
        this.landscape = info.result[0].list[0].LandscapeImage
        this.title_landsacape = info.result[0].list[0].Title
        this.summary_landsacape = info.result[0].list[0].Summary
        
        for (var count = 0; count < 4; count++) {
          this.four_movies.title.push(info.result[1].list[count].Title)
          this.four_movies.summary.push(info.result[1].list[count].Summary)
          this.four_movies.portrait.push(info.result[1].list[count].ThumbImage)       
        }
        console.log(info.result[1])
      });
  },
};
</script>