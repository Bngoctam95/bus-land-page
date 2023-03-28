<template>
  <header class="header">
    <nav>
      <div class="header__left">
        <ul class="header__menu">
          <li
            v-for="(item, index) in menuList"
            :key="index"
            class="header__menu__item"
          >
            <a href="/">{{ item.label }}</a>
          </li>
        </ul>
        <div class="header__logo">
          <a href="/"><img src="@/static/images/logo.svg" alt="figmaland" title="figmaland"></a>
        </div>
      </div>
      <div class="header__right">
        <ul class="header__socials">
          <li
            v-for="(item, index) in socialList"
            :key="index"
            class="header__socials__item"
          >
            <a href="/"><img :src="require(`@/static/images/${item.label}.svg`)" :alt="item.label" :title="item.label"></a>
          </li>
        </ul>
      </div>
    </nav>
    <!-- End desktop nav menu -->

    <nav class="mobile-nav">
      <div class="mobile-nav__logo">
        <a href="/"><img src="@/static/images/logo.svg" alt="figmaland" title="figmaland"></a>
      </div>
      <div class="mobile-nav__icon" @click="toggleMobileMenu">
        <img src="@/static/images/icon-nav.svg" alt="icon">
      </div>
    </nav>
    <div class="mobile-menu" :class="{ 'active': isMobileMenuActive }">
      <div class="close-icon" @click="toggleMobileMenu">
        <img src="@/static/images/close-icon.png" alt="Close">
      </div>
      <ul>
        <li
          v-for="(item, index) in menuList"
          :key="index"
        >
          <a href="/">{{ item.label }}</a>
        </li>
      </ul>
    </div>
    <!-- End mobile nav menu -->
  </header>
</template>

<script>

export default {
  name: 'PageHeader',
  data () {
    return {
      isMobileMenuActive: false,
      menuList: [
        {
          id: 1,
          label: 'Home'
        },
        {
          id: 2,
          label: 'Product'
        },
        {
          id: 3,
          label: 'Pricing'
        },
        {
          id: 4,
          label: 'About'
        },
        {
          id: 5,
          label: 'Contact'
        }
      ],
      socialList: [
        {
          id: 1,
          label: 'twitter'
        },
        {
          id: 2,
          label: 'facebook'
        },
        {
          id: 3,
          label: 'linkedin'
        }
      ]
    }
  },
  mounted () {
    window.addEventListener('scroll', this.handleHeaderScroll)
  },
  beforeUnmount () {
    window.removeEventListener('scroll', this.handleHeaderScroll)
  },
  methods: {
    handleHeaderScroll () {
      const header = document.querySelector('header')
      if (window.scrollY > 60) {
        header.classList.add('scroll')
      } else {
        header.classList.remove('scroll')
      }
    },
    toggleMobileMenu () {
      this.isMobileMenuActive = !this.isMobileMenuActive
    }
  }

}
</script>

<style lang="scss" scoped>
  header {
    position: fixed;
    z-index: 100;
    width: 100%;
    height: 156px;
    transition: all 300ms linear;
  }

  header.scroll {
    background-color: rgba(37, 43, 66, 0.95);
    box-shadow: 0 16px 14px -8px rgba(0, 0, 0, 0.3);
  }

  nav {
    max-width: 1210px;
    height: 100%;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
  }

  .header__left, .header__socials {
    display: flex;
    align-items: center;
  }

  .header__menu {
    display: flex;
    margin-left: 40px;
    gap: 21px;

    &__item a{
      font-weight: 400;
      font-size: 1.5rem;
      line-height: 28px;
      text-align: center;
      letter-spacing: 0.2px;
      color: #FFFFFF;
      text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    }
  }

  .header__logo {
    width: 186px;
    height: 58px;
    margin-left: 25px;
  }

  .header__socials {
    height: 100%;
    margin-right: 40px;
    gap: 24px
  }

  nav.mobile-nav, .mobile-menu {
      display: none;
    }

  @media (max-width: 1110px) {
    header {
      height: 112px;
    }
  }

  @media (max-width: 820px) {
    header {
      height: 112px;
    }
    .header__logo {
      display: none;
    }

    .header__menu__item a {
      font-size: 1.4rem;
    }

    .header__socials__item img {
      width: 30px;
      height: 100%;
    }
  }
  @media (max-width: 650px) {
    header {
      width: 100%;
      height: 112px;
    }

    nav {
      display: none;
    }

    nav.mobile-nav {
      display: flex;
      align-items: center;
      padding: 17px 16px;
    }

    .mobile-menu {
      position: fixed;
      height: 100vh;
      width: 100%;
      top: 0;
      left: 100%;
      background-color: #333;
      display: flex;
      justify-content: center;
      padding-top: 100px;
      transition: all 400ms ease;
    }

    .mobile-nav__icon {
      cursor: pointer;
    }

    .mobile-menu.active {
      left: 0;
    }

    .close-icon {
      width: 25px;
      height: 25px;
      position: fixed;
      top: 40px;
      right: 50px;
      opacity: 0;
      pointer-events: none;
      transition: all 400ms ease;

      & img {
        width: 100%;
      }
    }

    .mobile-menu.active .close-icon {
      opacity: 1;
      pointer-events: auto;
      cursor: pointer;
    }

    ul {
      & li {
        padding: 10px 0;
        & a {
          color: white;
          font-size: 2rem;
        }
      }
    }
  }
</style>
