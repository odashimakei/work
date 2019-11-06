<template>
  <div id="app">
    <HeaderWrap />
    <transition mode="out-in">
      <router-view />
    </transition>
    <FooterWrap />
  </div>
</template>

<script>
import HeaderWrap from '@/components/HeaderWrap.vue'
import FooterWrap from '@/components/FooterWrap.vue'

export default {
  name: 'app',
  components: {
    HeaderWrap,
    FooterWrap
  }
}
</script>

<style lang="scss">
@import './assets/reset.css';
@import url('https://fonts.googleapis.com/css?family=Raleway&display=swap');
@import url('https://fonts.googleapis.com/css?family=Raleway:700&display=swap');
@import './assets/style/variables.scss';


#app {
  font-family: 'Avenir',  "游ゴシック体", "YuGothic", Arial, sans-serif;
  color: $text-color;
}
a{
  text-decoration: none;
  color: $text-color;
}
ul, ol{
  list-style: none;
}

.v-enter-active, .v-leave-active {
  transition: opacity .5s;
}
.v-enter, .v-leave-to {
  opacity: 0;
}
</style>
