<template>
  <div>
    <NavBar />
    <SubNav />
  </div>
</template>

<script>
import NavBar from "@/components/NavBar.vue";

import SubNav from "@/components/SubNavBar.vue";

export default {
  name: "HomeView",

  components: {
    NavBar,
    SubNav,
  },
};
</script>
