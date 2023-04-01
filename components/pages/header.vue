<template>
  <header class="header">
    <nav class="header__nav">
      <div class="header__left">
        <ul class="header__menu">
          <li
            v-for="(item, index) in menuList"
            :key="index"
            class="header__menu__item"
            @click="gotoPage(item.href)"
          >
            <a href="javascript:voild(0)">{{ item.label }}</a>
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
        <img src="@/static/images/close-icon.svg" alt="Close">
      </div>
      <ul @click="toggleMobileMenu">
        <li
          v-for="(item, index) in menuList"
          :key="index"
          class="header__menu__item"
          @click="gotoPage(item.href)"
        >
          <a href="javascript:voild(0)">{{ item.label }}</a>
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
          href: '/',
          label: 'Home'
        },
        {
          id: 2,
          href: '/product',
          label: 'Product'
        },
        {
          id: 3,
          href: '/pricing',
          label: 'Pricing'
        },
        {
          id: 4,
          href: '/about',
          label: 'About'
        },
        {
          id: 5,
          href: '/contact',
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
    gotoPage (href) {
      this.$router.push(href)
    },
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
  .header {
    position: fixed;
    z-index: 100;
    width: 100%;
    height: 156px;
    transition: all 300ms linear;

    &.scroll {
      background-color: rgba(37, 43, 66, 0.95);
      box-shadow: 0 16px 14px -8px rgba(0, 0, 0, 0.3);
    }

    &__nav {
      max-width: 1210px;
      height: 100%;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
    }

    &__left, &__socials {
      display: flex;
      align-items: center;
    }

    &__menu {
      display: flex;
      margin-left: 40px;
      gap: 21px;

      &__item a {
        font-weight: 400;
        font-size: 1.5rem;
        line-height: 28px;
        text-align: center;
        letter-spacing: 0.2px;
        color: #FFFFFF;
        text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);

        &:hover {
          color: var(--primary-color);
        }
      }
    }

    &__logo {
      width: 186px;
      height: 58px;
      margin-left: 25px;
    }

    &__socials {
      height: 100%;
      margin-right: 40px;
      gap: 24px;

      &__item:hover {
        background-color: var(--primary-color);
      }
    }
  }

  .mobile-nav, .mobile-menu {
    display: none;
  }

  @media (max-width: 1110px) {
    .header {
      height: 112px;
    }
  }

  @media (max-width: 820px) {
    .header {
      width: 100%;
      height: 112px;

      &__nav {
      display: none;
    }
    }

    .mobile-nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 17px 16px;

      &__icon {
        cursor: pointer;
      }
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

      &.active {
        left: 0;
      }

      &.active .close-icon {
        opacity: 1;
        pointer-events: auto;
        cursor: pointer;
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

        img {
          width: 100%;
        }
      }

      ul {
        width: 100%;
        text-align: center;
        li {
          padding: 10px 0;
          a {
            display: block;
            width: 100%;
            color: white;
            font-size: 2rem;
          }
        }
      }
    }
  }
</style>
