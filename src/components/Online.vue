<template>
  <div>
    <offline @detected-condition="handleConnectivityChange"> </offline>

    <div v-bind:class="[online ? 'on-line' : 'off-line']">
      <h1 v-if="online">I'm OnLine :)</h1>
      <h1 v-else>Ooh, OffLine... :(</h1>
    </div>
  </div>
</template>

<script>

import offline from "v-offline";

export default {
  name: "App",
  data() {
    return {
      online: "",
      offline: "",
    };
  },
  components: {
    offline,
  },
  methods: {
    handleConnectivityChange(status) {
      console.log(status);
      if (status) {
        this.online = "";
      } else {
        this.offline = " ";
      }
    },
  },
};
</script>
