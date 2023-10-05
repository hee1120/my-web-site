<template>
  <MainHeader></MainHeader>
  <router-view />
  <MainFooter></MainFooter>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import MainHeader from "./components/MainHeader.vue";
import MainFooter from "./components/MainFooter.vue";

export default defineComponent({
  components: {
    MainHeader,
    MainFooter,
  },
  // setup() {},
});
</script>

<style lang="scss">
html {
  font-size: 62.5%;
}
body {
  font-family: YakuHanJP_Noto, "Noto Sans JP", sans-serif;
  font-size: 1.4rem;
  color: #111;
  line-height: 2;
  letter-spacing: 0.06em;
  text-align: left;
  font-weight: 400;
  -webkit-text-size-adjust: 100%; //iOS用の文字サイズ
  -webkit-font-smoothing: antialiased; //MacOSとiOS用の文字サイズ調整用
  -moz-osx-font-smoothing: grayscale; //Firefoxらしい
  background-color: #f5f5f5;
}
a {
  color: #111;
  text-decoration: none;
}
a:hover {
  color: #111;
  text-decoration: none;
}
a:focus {
}
</style>
