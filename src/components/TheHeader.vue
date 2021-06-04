<template>
  <header class="header">
    <nav class="header-nav">
      <router-link to="/" @click="closeMenu">
        <div class="header-nav__logo">&lt;DN/&gt;</div>
      </router-link>

      <ul class="header-nav__menu" :class="{ 'active-m': isActiveMenu }">
        <li v-for="(item, idx) in pagesList" :key="idx" @click="closeMenu">
          <router-link :to="item.path">{{ item.title }}</router-link>
        </li>
      </ul>
      <button
        class="hamburger hamburger--collapse"
        type="button"
        v-if="menuBtn"
        @click="openMenu"
        ref="hamburger"
      >
        <span class="hamburger-box">
          <span class="hamburger-inner"></span>
        </span>
      </button>
      <!-- <button class="header-nav__btn" @click="openMenu" v-if="menuBtn">
        &times;
      </button> -->
    </nav>
  </header>
</template>

<script>
export default {
  data() {
    return {
      menuBtn: false,
      isActiveMenu: false,
      pagesList: [
        {
          title: "Главная",
          path: "/",
        },
        // {
        //   title: "Услуги",
        //   path: "/service",
        // },
        {
          title: "Портфолио",
          path: "/portfolio",
        },
        {
          title: "Контакты",
          path: "/contact",
        },
      ],
    };
  },
  methods: {
    openMenu() {
      let btn = this.$refs.hamburger;
      btn.classList.toggle("is-active");
      this.isActiveMenu = !this.isActiveMenu;
    },
    closeMenu() {
      let btn = this.$refs.hamburger;
      btn.classList.remove("is-active");
      this.isActiveMenu = false;
    },
  },
  mounted() {
    let width = document.body.clientWidth;
    width <= 576 ? (this.menuBtn = true) : (this.menuBtn = false);
  },
};
</script>

<style lang="scss">
@import "../hamburgers.min.css";
.header {
  width: 100%;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
}
.header-nav {
  display: flex;
  align-items: center;
  background: #1f1e1d;
  color: #fff;
  font-weight: 600;
  padding: 15px;
  &__menu {
    display: flex;
    border: none;
    li {
      background: #1f1e1d;
      font-size: 0.8em;
      margin-right: 20px;
      a {
        color: #fff;
        &:hover {
          transition: 0.3s ease-out;
          color: #f84525;
        }
      }
      .router-link-active {
        color: #f84525bd;
      }
    }
  }
  &__logo {
    color: #fff;
    padding: 8px 0;
    font-size: 1.2em;
    margin-right: 30px;
    text-transform: uppercase;
  }
}
@media (max-width: 1200px) {
}
@media (max-width: 992px) {
}
@media (max-width: 768px) {
}
@media (max-width: 576px) {
  .header-nav {
    justify-content: space-between;
    position: fixed;
    width: 100%;
    &__menu {
      flex-direction: column;
      position: fixed;
      top: 87px;
      left: 0;
      right: 0;
      padding-left: 15px;
      display: none;
      background: inherit;
      height: calc(100vh - 87px);
      li {
        font-size: 2em;
        line-height: 2em;
        margin: 20px 0;
      }
      &.active-m {
        -webkit-animation: scale-up-ver-top 0.4s
          cubic-bezier(0.39, 0.575, 0.565, 1) both;
        animation: scale-up-ver-top 0.4s cubic-bezier(0.39, 0.575, 0.565, 1)
          both;
        display: block;
        width: 100%;
      }
    }

    @-webkit-keyframes scale-up-ver-top {
      0% {
        -webkit-transform: scaleY(0.4);
        transform: scaleY(0.4);
        -webkit-transform-origin: 100% 0%;
        transform-origin: 100% 0%;
      }
      100% {
        -webkit-transform: scaleY(1);
        transform: scaleY(1);
        -webkit-transform-origin: 100% 0%;
        transform-origin: 100% 0%;
      }
    }
    @keyframes scale-up-ver-top {
      0% {
        -webkit-transform: scaleY(0.4);
        transform: scaleY(0.4);
        -webkit-transform-origin: 100% 0%;
        transform-origin: 100% 0%;
      }
      100% {
        -webkit-transform: scaleY(1);
        transform: scaleY(1);
        -webkit-transform-origin: 100% 0%;
        transform-origin: 100% 0%;
      }
    }

    .hamburger.is-active .hamburger-inner,
    .hamburger.is-active .hamburger-inner:after,
    .hamburger.is-active .hamburger-inner:before {
      background-color: #fff;
    }
    .hamburger-inner,
    .hamburger-inner::before,
    .hamburger-inner::after {
      background-color: #fff;
    }
    // display: none;
  }
}
</style>