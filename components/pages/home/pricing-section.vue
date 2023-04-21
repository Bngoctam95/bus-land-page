<template>
  <div class="wrapper">
    <div class="pricing">
      <div class="pricing__content">
        <h2>Pricing</h2>
        <p>
          Most calendars are designed for teams.<br>
          <span>Slate is designed for freelancers</span>
        </p>
      </div>
      <div class="pricing__order">
        <div class="pricing__order__free">
          <h2 class="title">
            Free
          </h2>
          <p class="subtitle">
            Organize across <br>
            all apps by hand
          </p>
          <div class="price">
            <p class="price__number">
              0
            </p>
            <div class="price__mth">
              <span>$</span>
              <p>Per Month</p>
            </div>
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <baseButton class="primary btn" @click="orderNow('free')">
            Order Now
          </baseButton>
        </div>
        <div class="pricing__order__standard">
          <h2 class="title">
            Standard
          </h2>
          <p class="subtitle">
            Organize across <br>
            all apps by hand
          </p>
          <div class="price">
            <p class="price__number">
              10
            </p>
            <div class="price__mth">
              <span>$</span>
              <p>Per Month</p>
            </div>
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <baseButton class="btn" @click="orderNow('standard')">
            Order Now
          </baseButton>
        </div>
        <div class="pricing__order__business">
          <h2 class="title">
            Business
          </h2>
          <p class="subtitle">
            Organize across <br>
            all apps by hand
          </p>
          <div class="price">
            <p class="price__number">
              99
            </p>
            <div class="price__mth">
              <span>$</span>
              <p>Per Month</p>
            </div>
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <div class="feature">
            Pricing Feature
          </div>
          <baseButton class="primary btn" @click="orderNow('business')">
            Order Now
          </baseButton>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import baseButton from '@/components/button/base-button.vue'
export default {
  name: 'PricingSection',
  components: {
    baseButton
  },
  data () {
    return {
      order: null
    }
  },
  methods: {
    orderNow (orderType) {
      this.$data.order = orderType
    }
  }
}
</script>

<style lang="scss" scoped>
  .wrapper {
    width: 100%;
    background-color: rgba(37, 43, 66, 1);
    .pricing {
      width: 1210px;
      max-width: 100%;
      margin: 0 auto;
      padding: 110px 50px;

      &__content {
        text-align: center;
        font-weight: 400;
        color: #FFFFFF;
        letter-spacing: 0.2px;
        padding-bottom: 80px;
        h2 {
          font-size: 4.8rem;
          line-height: 55px;
          margin-bottom: 20px;
        }

        p {
          font-size: 2.8rem;
          line-height: 40px;
        }
      }

      &__order {
        display: flex;
        justify-content: space-around;
        align-items: center;

        &__free, &__business, &__standard {
          width: 335px;
          height: 607px;
          padding: 40px;
          text-align: center;
          background-color: white;
          border: 1px solid #DEDEDE;
          box-shadow: 0px 13px 19px rgba(0, 0, 0, 0.07);
          border-radius: 10px;

          .title {
            font-family: 'Graphik-Medium';
            font-weight: 700;
            font-size: 2rem;
            line-height: 28px;
            letter-spacing: 0.1px;
            text-transform: uppercase;
            color: #252B42;
          }

          .subtitle {
            font-weight: 400;
            font-size: 1.6rem;
            line-height: 23px;
            letter-spacing: 0.1px;
            color: #374754;
          }

          .price {
            padding: 30px 0;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;

            &__number {
              font-family: 'Graphik-Medium';
              font-weight: 700;
              font-size: 7.4rem;
              line-height: 84px;
              letter-spacing: 0.2px;
              color: #252B42;
            }

            &__mth {
              text-align: left;
              padding-top: 10px;
              span {
                font-family: 'Graphik-Medium';
                font-weight: 700;
                font-size: 2rem;
                line-height: 28px;
                letter-spacing: 0.1px;
                color: #252B42;
              }
              p {
                font-family: 'Graphik-Light';
                font-weight: 400;
                font-size: 1.6rem;
                line-height: 23px;
                letter-spacing: 0.1px;
                color: #374754;
              }
            }
          }

          .feature {
            padding: 10px;
            font-weight: 400;
            font-size: 1.5rem;
            line-height: 28px;
            letter-spacing: 0.2px;
            color: #252B42;
          }

          .btn {
            margin-top: 10px;
          }
        }

        &__standard {
          height: 693px;
          padding: 83px 40px;
          background-color: var(--primary-color);

          .title, .subtitle, .feature {
            color: white;
          }
          .price {
            &__number {
              color: white;
            }

            &__mth {
              span {
                color: white;
              }
              p {
                color: white;
              }
            }
          }
        }
      }
    }
  }

  /* Responsive */
  @media (max-width: 1150px) {
    .wrapper {
      .pricing {
        &__order {
          &__free, &__business, &__standard {
            width: 255px;
            padding: 40px 0;
          }
        }
      }
    }
  }

  @media (max-width: 810px) {
    .wrapper {
      .pricing {
        &__order {
          &__free, &__business, &__standard {
            width: 200px;
          }
        }
      }
    }
  }

  @media (max-width: 650px) {
    .wrapper {
      .pricing {
        &__order {
          &__free, &__business, &__standard {
            width: 335px;
          }
          flex-direction: column;
          gap: 50px
        }
        &__content {
          p {
            span {
              display: none;
            }
          }
        }
      }
    }
  }
</style>
