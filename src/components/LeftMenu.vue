<template>
    <div class="side-menu-wrapper left">
      <ul class="side_menu">
        <li class="side_menu-item" v-for="item in menu" v-bind:key="item.id">
          <a href="">{{item.title}}</a>
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
          title: "hello",
          href: "/hi",
        },
        {
          title: "hi",
          href: "/hi",
        },
        {
          title: "aksfjdgafs",
          href: "/hi",
        },
        {
          title: "asgdasdg",
          href: "/hi ",
        },
      ],
    };
  },
};
</script>