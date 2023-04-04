<template>
  <div class="banner">
    <img class="banner__img" src="@/static/images/banner.png" alt="Banner Image">
    <div class="banner__content">
      <h1 class="banner__title">
        The best products start with Figma
      </h1>
      <h2 class="banner__subtitle">
        Most calendars are designed for teams. Slate is designed for freelancers
      </h2>
      <base-button class="primary banner__btn">
        Try For Free
      </base-button>
    </div>
  </div>
</template>

<script>
import baseButton from '@/components/button/base-button.vue'
export default {
  name: 'BannerSection',
  components: {
    baseButton
  }
}
</script>

<style lang="scss" scoped>
  .banner {
    position: relative;
    width: 100%;

    &__img {
      width: 100%;
    }

    &__content {
      position: absolute;
      top: 25%;
      left: 50%;
      transform: translateX(-50%);
      text-align: center;
    }

    &__title {
      margin-bottom: 20px;
      font-size: 7.4rem;
      color: #ffffff;
      line-height: 84px;
      letter-spacing: 0.2px;
    }

    &__subtitle {
      margin-bottom: 40px;
      font-size: 2.8rem;
      color: #ffffff;
      line-height: 40px;
      letter-spacing: 0.2px;
    }

  }

  /* Resonsive */
  @media (max-width: 1306px) {
    .banner {

      &__content {
        top: 32%;
      }

      &__title {
        font-size: 6.5rem;
        line-height: 70px;
      }

      &__subtitle {
        font-size: 2.2rem;
        line-height: 30px;
      }

      &__btn {
        font-size: 1.8rem;
        padding: 12px 35px;
      }
    }
  }

  @media (max-width: 1180px) {
    .banner {
      &__content {
        top: 30%;
      }

      &__title {
        font-size: 6.2rem;
        line-height: 65px;
      }

      &__subtitle {
        font-size: 2rem;
        line-height: 25px;
      }

      &__btn {
        font-size: 1.6rem;
        padding: 12px 30px;
      }
    }
  }

  @media (max-width: 1100px) {
    .banner {
      &__content {
        top: 26%;
      }

      &__title {
        font-size: 5.5rem;
        line-height: 55px;
      }

      &__subtitle {
        font-size: 1.9rem;
        line-height: 23px;
      }

      &__btn {
        font-size: 1.5rem;
        padding: 11px 25px;
      }
    }
  }

  @media (max-width: 980px) {
    .banner {
      &__content {
        top: 22%;
      }

      &__title {
        font-size: 4rem;
        line-height: 45px;
      }

      &__subtitle {
        font-size: 1.8rem;
        line-height: 22px;
      }

      &__btn {
        font-size: 1.4rem;
        padding: 10px 25px;
      }
    }
  }

  @media (max-width: 820px) {
    .banner {
      &__content {
        top: 18%;
      }

      &__title {
        font-size: 3.6rem;
        line-height: 45px;
        margin-bottom: 15px;
      }

      &__subtitle {
        font-size: 1.6rem;
        line-height: 22px;
        margin-bottom: 25px;
      }

      &__btn {
        font-size: 1.4rem;
        padding: 10px 25px;
      }
    }
  }

  @media (max-width: 650px) {
    .banner {
      width: 100%;
      height: 110vh;

      &__img {
        height: 100%;
        object-fit: cover;
      }

      &__content {
        width: 100%;
        padding: 0 30px;
        top: 280px;
      }

      &__title {
        font-size: 4rem;
        font-weight: 200;
        line-height: 50px;
        letter-spacing: 0.4px;
      }

      &__subtitle {
        font-size: 1.8rem;
        font-weight: 200;
        line-height: 30px;
        letter-spacing: 0.8px;
      }

      &__btn {
        font-size: 1.4rem;
        padding: 10px 25px;
      }
    }
  }
  @media (max-width: 400px) {
    .banner {
      &__content {
        top: 180px;
      }
    }
  }
</style>
