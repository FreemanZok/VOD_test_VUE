<template>
  <div class="pages-wrapper">
    <a href="" class="pages_item">previous</a>
    <a href="" class="pages_item" 
    v-for="item in 3" 
    v-bind:key="item.id"
      >
      {{item}}
    </a>
    <a href="" class="pages_item">...</a>
    <a href="" class="pages_item">next</a>
  </div>
</template>
<script>

export default {
  name: "PageNumbers",
};
</script>