<template>
  <header>
    <nav class="sp">
      <div class="slide-menu-btn">
        <a class="menu-trigger" @click="toggleSlideMenu()">
          <span></span>
          <span></span>
        </a>
        <!-- 押したらactiveクラスをつける予定 -->
      </div>

      <div class="slide-menu-nav">
        <!-- 押したらopenクラスをつける予定 -->
        <a href="header-logo"></a>
        <!-- <ul>
          <li
            v-for="(item, index) in navList"
            :key="item.name"
            :class="'nav-' + index"
          >
            <router-link :to="item.url">{{ item.name }}</router-link>
          </li>
        </ul> -->
      </div>
    </nav>
    <nav class="header-gnav-pc pc">
      <!-- <ul class="header-pc-gnav-list">
        <li
          v-for="(item, index) in navList"
          :key="item.name"
          :class="'nav-' + index"
        >
          <router-link :to="item.url">{{ item.name }}</router-link>
        </li>
      </ul> -->
    </nav>
  </header>
</template>

<script lang="ts">
import { ref, defineComponent, onBeforeMount } from "vue";
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";
import navList from "../types/nav-list";

export default defineComponent({
  setup() {
    const isSlideMenuOpen = ref<boolean>(false);

    const toggleSlideMenu = () => {
      console.log("clicked");
      isSlideMenuOpen.value = !isSlideMenuOpen.value; //真偽値を逆にしてる
    };

    const sayHelloWorld = (): void => {
      console.log("hello world");
    };

    onBeforeMount(() => {
      console.log(sayHelloWorld());
    });

    return {
      navList,
      toggleSlideMenu,
    };
  },
});
</script>

<style lang="scss" scoped>
/* menu-trigger */
.menu-trigger,
.menu-trigger span {
  display: inline-block;
  transition: all 0.3s;
  box-sizing: border-box;
}
.menu-trigger {
  position: relative;
  width: 50px;
  height: 50px;
  background-color: #fff;

  span {
    position: absolute;
    left: 0;
    width: 24px;
    height: 1px;
    background-color: #111;
  }
  span:nth-of-type(1) {
    top: 21px;
    left: 13px;
  }
  span:nth-of-type(2) {
    bottom: 22px;
    left: 13px;
  }
}

.menu-trigger.active {
  span {
    background-color: #111;
  }
  span:nth-of-type(1) {
    -webkit-transform: translateY(3px) rotate(-45deg);
    transform: translateY(3px) rotate(-45deg);
  }
  span:nth-of-type(2) {
    -webkit-transform: translateY(-3px) rotate(45deg);
    transform: translateY(-3px) rotate(45deg);
  }
}
nav {
  position: fixed; //要素を画面から移動しなくする
  top: 0;
  right: 0;
  z-index: 10000;

  ul {
    list-style-type: none;
    display: flex;
    padding: 15px 80px;

    li:not(:last-child) {
      margin-right: 50px;
    }

    li {
      a {
        color: #111;
        transition: 0.5s;
      }
      a:hover {
        color: #999;
        text-decoration: none;
      }
    }
  }
}
</style>
