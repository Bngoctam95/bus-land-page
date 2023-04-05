<template>
  <div class="wrapper">
    <div class="footer">
      <div class="footer__pages">
        <h2 class="footer__pages__heading">
          Pages
        </h2>
        <ul class="footer__pages__list">
          <li
            v-for="(item, index) in menuList"
            :key="index"
            class="footer__pages__item"
            @click="gotoPage(item.href)"
          >
            <a href="javascript:voild(0)">{{ item.label }}</a>
          </li>
        </ul>
      </div>
      <div class="footer__tom">
        <h2 class="footer__tom__heading">
          Tomothy
        </h2>
        <ul class="footer__tom__list">
          <li>
            Eleanor Edwards
          </li>
          <li>
            Ted Robertson
          </li>
          <li>
            Annette Russell
          </li>
          <li>
            Jennie Mckinney
          </li>
          <li>
            Gloria Richards
          </li>
        </ul>
      </div>
      <div class="footer__jane">
        <h2 class="footer__jane__heading">
          Jane Black
        </h2>
        <ul class="footer__jane__list">
          <li>
            Eleanor Edwards
          </li>
          <li>
            Ted Robertson
          </li>
          <li>
            Annette Russell
          </li>
          <li>
            Jennie Mckinney
          </li>
          <li>
            Gloria Richards
          </li>
        </ul>
      </div>
      <div class="footer__infor">
        <div class="footer__infor__map">
          <img src="@/static/images/footer-map.svg" alt="">
          <p>7480 Mockingbird Hill undefined</p>
        </div>
        <div class="footer__infor__phone">
          <img src="@/static/images/footer-phone.svg" alt="">
          <p>(239) 555-0108</p>
        </div>
        <div class="footer__infor__socials">
          <img src="@/static/images/twitter.svg" alt="">
          <img src="@/static/images/facebook.svg" alt="">
          <img src="@/static/images/linkedin.svg" alt="">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PageFooter',
  data () {
    return {
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
      ]
    }
  },
  methods: {
    gotoPage (href) {
      this.$router.push(href)
    }
  }
}
</script>

<style lang="scss" scoped>
  .wrapper {
    width: 100%;
    background-color:rgba(37, 43, 66, 1);

    .footer {
      width: 991px;
      max-width: 100%;
      margin: 0 auto;
      padding: 150px 0;
      display: flex;
      justify-content: space-between;

      &__pages, &__tom, &__jane {
        color: #FFFFFF;

        &__heading {
          font-family: 'Graphik-Regular';
          font-weight: 700;
          font-size: 2rem;
          line-height: 28px;
          letter-spacing: 0.1px;
        }

        &__list {
          li {
            padding: 8px 0;
            font-weight: 400;
            font-size: 1.5rem;
            line-height: 28px;
            letter-spacing: 0.2px;
            color: #FFFFFF;

            a {
              color: #FFFFFF;
            }
          }
        }
      }

      &__pages {
        &__list {
          li {
            a:hover {
              color: var(--primary-color);
            }
          }
        }
      }

      &__infor {
        color: #FFFFFF;

        &__map, &__phone {
          margin-bottom: 20px;
          display: flex;
          align-items: center;
          gap: 10px;

          p {
            font-weight: 400;
            font-size: 1.5rem;
            line-height: 27px;
            letter-spacing: 0.2px;
          }
        }

        &__socials {
          img {
            margin-right: 25px;
          }
        }
      }
    }
  }

  /* Responsive */
  @media (max-width: 1150px) {
    .wrapper {
      .footer {
        padding: 150px 40px;
        &__infor {
          &__socials {
            img {
              margin-right: 5px;
            }
          }
        }
      }
    }
  }
  @media (max-width: 850px) {
    .wrapper {
      .footer {
        flex-direction: column;
        align-items: center;
        gap: 40px;
      }
    }
  }
</style>
