<template>
  <nav class="menu">
    <div class="menu__logo">HERE IS PLACE FOR LOGO...</div>
    <div @click="showList" class="menu__hamburger">
      <div class="menu__bar menu__bar--top" :class="{rotateSub45: visible}"></div>
      <div class="menu__bar menu__bar--middle" :class="{invisible: visible}"></div>
      <div class="menu__bar menu__bar--bottom" :class="{rotateAdd45: visible}"></div>
    </div>
    <transition name="list">
      <ul class="menu__list" v-if="visible">
        <li class="menu__list__item">home</li>
        <li class="menu__list__item">about</li>
        <li class="menu__list__item">blog</li>
        <li class="menu__list__item">kitchen</li>
        <li class="menu__list__item">contact</li>
      </ul>
    </transition>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      visible: true
    };
  },
  created() {
    window.addEventListener("resize", () => {
      if (window.innerWidth > 800) {
        this.visible = true;
      } else {
        this.visible = false;
      }
    });
  },
  methods: {
    showList() {
      this.visible = !this.visible;
    }
  }
};
</script>

<style lang="css">
* {
  margin: 0;
  padding: 0;
  font-family: "Jost", sans-serif;
}
@keyframes list {
  0% {
    opacity: 0;
  }
  10% {
    opacity: 0.1;
  }
  20% {
    opacity: 0.2;
  }
  30% {
    opacity: 0.3;
  }
  40% {
    opacity: 0.4;
  }
  50% {
    opacity: 0.5;
  }
  60% {
    opacity: 0.6;
  }
  70% {
    opacity: 0.7;
  }
  80% {
    opacity: 0.8;
  }
  90% {
    opacity: 0.9;
  }
  100% {
    opacity: 1;
  }
}
.list-enter-active {
  animation: list 0.3s ease-in;
}
.list-leave-active {
  animation: list 0.3s ease-in reverse;
}
.menu {
  position: fixed;
  width: 100vw;
  background-color: rgba(255, 255, 255, 0.5);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  border: 1px solid black;
}

.menu__logo {
  padding: 10px;
  text-align: center;
}
.menu__hamburger {
  width: 30px;
  height: 30px;
  position: relative;
  left: 50%;
  transform: translateX(-50%);
  margin-bottom: 10px;
}
.menu__hamburger:hover {
  cursor: pointer;
}
.menu__bar {
  transform-origin: center;
  width: 100%;
  height: 6px;
  background-color: #ff6961;
  position: absolute;
  transition: 0.3s ease-in;
}

.menu__bar--middle {
  transform: translateY(50%);
  bottom: 50%;
}
.invisible {
  opacity: 0;
}
.menu__bar--bottom {
  bottom: 0;
}
.rotateSub45 {
  transform: translateY(12px) rotate(-45deg);
}
.rotateAdd45 {
  transform: translateY(-12px) rotate(45deg);
}
.menu__list {
  flex-direction: column;
  list-style: none;
  display: flex;
  padding: 10px;
  transition: 0.3s ease-in;
}
.menu__list__item {
  font-size: 12px;
  padding: 5px;
  text-align: center;
  text-transform: uppercase;
}
.menu__list__item:hover {
  cursor: pointer;
  color: #ff6961;
}
@media (min-width: 800px) {
  .menu {
    flex-direction: row;
  }
  .menu__list {
    width: 60%;
    flex-direction: row;
    justify-content: space-between;
  }
  .menu__hamburger {
    display: none;
  }
  .menu__list__item {
    flex-basis: 15%;
    transition: 0.3s linear;
  }
  .menu__list__item:hover {
    border-bottom: 1px solid #ff6961;
  }
}
@media (min-width: 800px) {
  .menu {
    flex-direction: row;
  }
  .menu__list {
    z-index: 2;
    width: 60%;
    flex-direction: row;
    justify-content: space-between;
  }
  .menu__hamburger {
    display: none;
  }
  .menu__list__item {
    flex-basis: 15%;
    transition: 0.3s linear;
    font-size: 16px;
  }
  .menu__list__item:hover {
    border-bottom: 1px solid #ff6961;
  }
}
@media (min-width: 1024px) {
  .menu__list {
    width: 50%;
  }
}
@media (min-width: 1280px) {
  .menu__list {
    width: 50%;
  }
}
@media (min-width: 1440px) {
  .menu__list {
    width: 45%;
    font-size: 18px;
  }
}
</style>
