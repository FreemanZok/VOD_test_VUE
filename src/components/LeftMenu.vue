<template>
    <div class="side-menu-wrapper left">
      <ul class="side_menu">
        <li class="side_menu-item" v-for="item in 20" v-bind:key="item.id">
          <a href="">actors</a>
        </li>
      </ul>
    </div>
</template>

<script>
export default {
  name: "LeftMenu",
  data: function () {
    return {
      menu: [
        {
          title: "home",
          href: "./akbarAagha",
        },
        {
          title: "hocelebretiesme",
          href: "./akbarAagha",
        },
        {
          title: "nasder",
          href: "./akbarAagha",
        },
        {
          title: "hoveida",
          href: "./akbarAagha",
        },
      ],
    };
  },
};
</script>