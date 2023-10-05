<template>
  <footer id="footer">
    <div class="footer-logo">footer-logoが入るよ</div>
    <a href="" alt="my-name"></a>
    <nav>
      <ul class="footer-gnav">
        <li v-for="item in navList" :key="item.name">
          <router-link :to="item.url">{{ item.name }}</router-link>
        </li>
      </ul>
    </nav>
  </footer>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import navList from "@/types/nav-list";

export default defineComponent({
  setup() {
    return {
      navList,
    };
  },
});
</script>

<style lang="scss" scoped>
footer {
  position: relative;
  padding: 80px 0 26px;

  .footer-logo {
    margin-bottom: 40px;
  }
  nav {
    .footer-gnav {
      list-style: none;
      text-align: center;

      li {
        margin-bottom: 15px;

        a {
          display: inline-block; //横並びにする
          font-family: "Lato", sans-serif;
          font-size: 1.5rem; //rem(root em): ルート要素のフォントに対する相対的なサイズ
          line-height: 1.4; //行間の高さがfont-sizeの1.4倍
          letter-spacing: 0.05em;
          transition: color 0.3s;
        }
        a:hover {
          color: #999;
        }
      }
      li:last-child {
        margin-bottom: 0;
      }
    }
  }
}
</style>
