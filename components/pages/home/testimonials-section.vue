<template>
  <div class="wrapper">
    <div class="testimonials">
      <h2 class="testimonials__title">
        Testimonials
      </h2>
      <img class="testimonials__img" src="@/static/images/ibm.png" alt="">
      <p class="testimonials__content">
        Most calendars are designed for teams. Slate is designed for freelancers
        who want a simple way to plan their schedule.
      </p>
      <div class="testimonials__avatar">
        <img src="@/static/images/avatar.png" alt="">
        <div class="testimonials__avatar__content">
          <p>Organize across</p>
          <p>Ui designer</p>
        </div>
      </div>
      <baseButton class="primary testimonials__btn">
        More Testimonials
      </baseButton>
    </div>
  </div>
</template>

<script>
import baseButton from '@/components/button/base-button.vue'
export default {
  name: 'TestimonialsSection',
  components: {
    baseButton
  }
}
</script>

<style lang="scss" scoped>
  .wrapper {
    width: 100%;
    .testimonials {
      max-width: 1210px;
      width: 100%;
      margin: 0 auto;
      text-align: center;
      padding: 110px 0;
      color: var(--text-color);
      &__title {
        margin-bottom: 80px;
        font-weight: 400;
        font-size: 4.8rem;
        line-height: 55px;
        letter-spacing: 0.2px;

      }

      &__img {
        margin-bottom: 60px;
      }

      &__content {
        margin-bottom: 60px;
        padding: 0 120px;
        font-weight: 400;
        font-size: 2.8rem;
        line-height: 40px;
        letter-spacing: 0.2px;
      }

      &__avatar {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 15px;
        margin-bottom: 60px;

        &__content {
          font-weight: 400;
          font-size: 1.6rem;
          line-height: 25px;
          letter-spacing: 0.1px;
          text-align: left;
        }
      }

      &__btn {
        font-family: 'Graphik-Regular';
        font-weight: 700;
        font-size: 2rem;
      }
    }
  }

  /* Responsive */
  @media (max-width: 950px) {
    .wrapper {
      .testimonials {
        padding: 110px 60px;

        &__content {
          padding: 0;
          font-size: 2.2rem;
          font-weight: bolder;
          line-height: 30px;
        }
      }
    }
  }
  @media (max-width: 500px) {
    .wrapper {
      .testimonials {
        padding: 110px 40px;

        &__content {
          font-size: 1.8rem;
        }
      }
    }
  }
</style>
