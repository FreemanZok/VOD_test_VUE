<template>
  <div class="others_movies clearfix">
    <div
      class="others_movies-wrapper"
      v-for="(item, a) in 10"
      v-bind:key="item.id"
    >
      <div class="others_movies_img-wrapper">

        <img class="inner-img img-others" :src="four_movies.thumb_image[a]"/>
      </div>
      <div class="others_movies_title">{{four_movies.title[a]}}</div>
    </div>
  </div>
</template>
<script>
export default {
  name: "OtherMovies",
  data: function () {
    return {
      four_movies: {
          title: [],
          thumb_image:[],
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
        
        for (var count = 0; count < 10; count++) {
          this.four_movies.title.push(info.result[2].list[count].Title)
          this.four_movies.thumb_image.push(info.result[2].list[count].PortraitImage)       
        }
      });
  },
};
</script>