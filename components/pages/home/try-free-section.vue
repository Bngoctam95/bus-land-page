<template>
  <div class="wrapper">
    <div class="tryfree">
      <div class="tryfree__content">
        <h3>
          Fastest way to organize
        </h3>
        <p>
          Most calendars are designed for teams.<br>
          <span>Slate is designed for freelancers</span>
        </p>
        <baseButton class="primary tryfree__btn">
          Try For Free
        </baseButton>
      </div>
      <div class="tryfree__images">
        <img src="@/static/images/macbook.png" alt="">
      </div>
    </div>
  </div>
</template>

<script>
import baseButton from '@/components/button/base-button.vue'
export default {
  name: 'TryFreeSection',
  components: {
    baseButton
  }
}
</script>

<style lang="scss" scoped>
  .wrapper {
    width: 100%;
    .tryfree {
      max-width: 1210px;
      width: 100%;
      margin: 0 auto;
      padding: 226px 0;
      display: flex;
      justify-content: space-between;
      gap: 50px;
      &__content {
        color: var(--text-color);
        h3 {
          margin-bottom: 40px;
          font-weight: 400;
          font-size: 4.8rem;
          line-height: 55px;
          letter-spacing: 0.2px;
        }
        p {
          margin-bottom: 70px;
          font-weight: 400;
          font-size: 2.8rem;
          line-height: 40px;
          letter-spacing: 0.2px;
        }
      }

      &__images {
        img {
          width: 100%;
        }
      }
    }
  }

  /* Responsive */
  @media (max-width: 1250px) {
    .wrapper {
      .tryfree {
       padding: 226px 50px;
        &__content {
          h3 {
            margin-bottom: 20px;
            font-size: 4.4rem;
            line-height: 45px;
          }
          p {
            margin-bottom: 50px;
            font-size: 2.4rem;
            line-height: 30px;
          }
        }

      }
    }
  }

  @media (max-width: 1120px) {
    .wrapper {
      .tryfree {
        gap: 30px;
        &__content {
          h3 {
            font-size: 4.2rem;
          }
          p {
            margin-bottom: 40px;
            font-size: 2.2rem;
          }
        }
      }
    }
  }

  @media (max-width: 1050px) {
    .wrapper {
      .tryfree {
        gap: 20px;
        &__content {
          h3 {
            margin-bottom: 20px;
            font-size: 3.8rem;
          }
          p {
            margin-bottom: 20px;
            font-size: 2rem;
          }
        }
        &__btn {
          padding: 15px 40px;
        }

        &__images {
          width: 480px;
        }
      }
    }
  }

  @media (max-width: 950px) {
    .wrapper {
      .tryfree {
        padding: 226px 30px;
        flex-direction: column;
        align-items: center;

        &__content {
          text-align: center;
          margin-bottom: 40px;
          h3 {
            margin-bottom: 40px;
          }
          p {
            margin-bottom: 40px;

            span {
              display: none;
            }
          }
        }
        &__images {
          width: 100%;
        }
      }
    }
  }

  @media (max-width: 500px) {
    .wrapper {
      .tryfree {
        &__content {
          p {
            padding: 0 50px;
          }
        }
      }
    }
  }
</style>
