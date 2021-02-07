<template>
  <div class="header">
    <div class="header_top clearfix container">
      <div class="left header_top-part">
        <a href="" class="header_login-buttons">Login</a>
        <a href="" class="header_login-buttons">Entries</a>
      </div>
      <div class="right header_top-part">
        <div class="search_wrapper">
          <input type="text" />
          <img src="../assets/img/5.png" alt="" />
        </div>
        <a class="hamburger right" v-on:click="show_it">
          <div class="line"></div>
        </a>
      </div>
    </div>

    <div class="header_bottom clearfix">
      <div class="container clearfix">
        <div class="img-wrapper left logo">
          <img src="../assets/img/6.png" />
        </div>
        <ul class="right header_menu">
          <li class="header_menu-item">
            <a :href="item.href" class="click" v-for="item in menu" :key="item">
              {{ item.title }}
            </a>
          </li>
        </ul>
        <ul class="header_menu -small" :class="{ show: showIt, hide: hideIt }">
          <div class="close" @click="hide_it">
            <svg
              version="1.1"
              id="Layer_1"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
              x="0px"
              y="0px"
              width="122.878px"
              height="122.88px"
              viewBox="0 0 122.878 122.88"
              enable-background="new 0 0 122.878 122.88"
              xml:space="preserve"
            >
              <g>
                <path
                  d="M1.426,8.313c-1.901-1.901-1.901-4.984,0-6.886c1.901-1.902,4.984-1.902,6.886,0l53.127,53.127l53.127-53.127 c1.901-1.902,4.984-1.902,6.887,0c1.901,1.901,1.901,4.985,0,6.886L68.324,61.439l53.128,53.128c1.901,1.901,1.901,4.984,0,6.886 c-1.902,1.902-4.985,1.902-6.887,0L61.438,68.326L8.312,121.453c-1.901,1.902-4.984,1.902-6.886,0 c-1.901-1.901-1.901-4.984,0-6.886l53.127-53.128L1.426,8.313L1.426,8.313z"
                />
              </g>
            </svg>
          </div>
          <li class="header_menu-item">
            <a :href="item.href" class="click" v-for="item in menu" :key="item">
              {{ item.title }}
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  data: function () {
    return {
      menu: [
        {
          title: "home",
          href: "",
        },
        {
          title: "hocelebretiesme",
          href: "",
        },
        {
          title: "nasder",
          href: "",
        },
        {
          title: "hoveida",
          href: "",
        },
      ],
      showIt: false,
      hideIt: true,
    };
  },
  methods: {
    show_it: function () {
      this.showIt = true;
      this.hideIt = false;
    },
    hide_it: function () {
      this.showIt = false;
      this.hideIt = true;
    },

  },
};
</script>

