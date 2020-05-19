<template>
  <header class="header">
    <div class="header__title">
      <h1 class="header__main-title">Powerlifting</h1>
      <h3 class="header__desc">Squat, Benchpress, Dealift...</h3>
      <h4 class="header__desc">Are you ready?</h4>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {};
  },

  methods: {}
};
</script>

<style lang="css">
.header {
  height: 100vh;
  background-image: url("../images/header__bg.jpg");
  background-position: center;
  background-size: cover;
}
.header__title {
  text-align: center;
  /* z-index: -1; */
  text-transform: uppercase;
  position: absolute;
  top: 35%;
  left: 50%;
  /* font-size: 35px; */
  transform: translateX(-50%);
}
.header__main-title {
  font-size: 35px;
}
.header__desc {
  font-size: 25px;
}
</style>
