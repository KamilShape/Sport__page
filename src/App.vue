<template>
  <div class="main_wrapper">
    <Menu></Menu>
    <Banner></Banner>
  </div>
</template>

<script>
import Menu from "./components/Menu.vue";
import Banner from "./components/Banner.vue";

export default {
  data() {
    return {};
  },
  components: {
    Menu,
    Banner
  }
};
</script>

<style lang="css">
body {
  margin: 0;
  padding: 0;
  font-family: "Jost", sans-serif;
}
</style>
