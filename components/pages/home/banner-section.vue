<template>
  <div class="banner">
    <img class="banner__img" src="@/static/images/banner.svg" alt="banner">
    <!-- <div class="banner__container">
      <h1 class="banner__title">
        The best products start with Figma
      </h1>
      <p class="banner__content">
        Most calendars are designed for teams. Slate is designed for freelancers
      </p>
      <button type="text" class="banner__btn">
        Try For Free
      </button>
    </div> -->
  </div>
</template>

<script>
export default {
  name: 'BannerSection'
}
</script>

<style lang="scss" scoped>
  .banner {
    height: 1042px;

    &__img {
      width: 100%;
    }

    &__container {
      width: 60%;
      position: absolute;
      top: 180px;
      left: 50%;
      transform: translateX(-50%);
      text-align: center;
    }

    &__title {
      font-family: 'Graphik-Medium';
      font-weight: 700;
      font-size: 7.4rem;
      line-height: 84px;
      text-align: center;
      letter-spacing: 0.2px;
      color: white;
    }

    &__content {
      font-weight: 400;
      font-size: 2.8rem;
      line-height: 40px;
      text-align: center;
      letter-spacing: 0.2px;
      color: white;
    }

    &__btn {
      padding: 14px 62px;
      margin: 0 auto;
      background: #2091F9;
      border-radius: 35px;
      border-color: transparent;
      font-family: 'Graphik-Light';
      font-weight: 400;
      font-size: 2rem;
      line-height: 20px;
      text-align: center;
      letter-spacing: 0.2px;
      color: #FFFFFF;
      cursor: pointer;

      &:hover {
        background: #0254a0;
      }
    }
  }

  @media (max-width: 1110px) {
    .banner {

      &__container {
        top: 100px;
      }

      &__title {
        font-size: 5rem;
        font-weight: 600;
        line-height: 65px;
      }

      &__content {
        margin: 15px 0;
        font-size: 2.5rem;
        line-height: 30px;
      }

      &__btn {
        margin-top: 15px;
      }
    }
   }

   @media (max-width: 800px) {
    .banner {

      &__container {
        top: 100px;
        width: 50%;
      }

      &__title {
        font-size: 4rem;
        line-height: 45px;
      }

      &__content {
        margin: 15px 0;
        font-size: 1.6rem;
        line-height: 20px;
      }

      &__btn {
        margin-top: 15px;
        padding: 8px 30px;
      }
    }
  }

  @media (max-width: 650px) {
    .banner{
      width: 100%;
      height: 750px;

      &__img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }
</style>
