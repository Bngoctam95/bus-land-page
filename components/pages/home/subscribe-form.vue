<template>
  <div class="wrapper">
    <div class="subscribe">
      <div class="subscribe__mobile">
        <h3 class="subscribe__mobile__title">
          At your fingertips
        </h3>
        <h3 class="subscribe__mobile__subtitle">
          Newsletter
        </h3>
        <p>
          Most calendars are designed for teams.<br>
          Slate is designed for freelancers
        </p>
      </div>
      <div class="subscribe__image">
        <img src="@/static/images/subscribe.png" alt="">
      </div>
      <div class="subscribe__content">
        <h3 class="subscribe__content__title">
          At your fingertips
        </h3>
        <h3 class="subscribe__content__subtitle">
          Lightning fast prototyping
        </h3>
        <h4>Subscribe to our Newsletter</h4>
        <p>Available exclusivery on Figmaland</p>
        <div class="subscribe__content__submit">
          <input v-model="email" type="email" name="email" placeholder="Your Email">
          <baseButton class="primary btn" @click="submitForm">
            Subscribe
          </baseButton>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import baseButton from '@/components/button/base-button.vue'
export default {
  name: 'SubscribeForm',
  components: {
    baseButton
  },
  data () {
    return {
      email: '',
      registeredEmails: []
    }
  },
  methods: {
    validateEmail () {
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
      if (!emailRegex.test(this.email)) {
        alert('Email không hợp lệ')
        return false
      }
      return true
    },
    submitForm () {
      if (!this.validateEmail()) {
        return true
      }
      this.registeredEmails.push(this.email)
      this.email = ''
    }
  }
}
</script>

<style lang="scss" scoped>
  .wrapper {
    width: 100%;
    .subscribe {
      max-width: 1210px;
      width: 100%;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      gap: 50px;

      &__mobile{
        display: none;
      }

      &__image {
        margin-top: 159px;
      }

      &__content {
        margin-top: 234px;

        &__title, h4 {
          font-family: 'Graphik-Medium';
          font-weight: 700;
          font-size: 2rem;
          line-height: 28px;
          letter-spacing: 0.1px;
          color: var(--text-color);
        }
        &__subtitle {
          margin: 17px 0 25px 0;
          font-family: 'Graphik-Regular';
          font-weight: 400;
          font-size: 4.8rem;
          line-height: 55px;
          letter-spacing: 0.2px;
          color: var(--text-color);
        }
        p {
          margin-top: 5px;
          font-family: 'Graphik-Light';
          font-weight: 400;
          font-size: 1.8rem;
          line-height: 25px;
          letter-spacing: 0.2px;
          color: #374754;
        }

        &__submit {
          margin-top: 36px;
          input {
            margin-right: 12px;
            background: #F4F4F4;
            border: 1px solid #E8E8E8;
            border-radius: 39px;
            padding: 18px 39px;
            font-family: 'Graphik-Light';
          }
        }
      }
    }
  }

/* Responsive */
@media (max-width: 1250px) {
  .wrapper {
    .subscribe {
      padding: 0 50px;

      &__image {
        width: 60%;
        img {
          width: 100%;
        }
      }
      &__content {
        margin-top: 200px;
        width: 40%;
          &__submit {
          margin-top: 20px;
            input {
            margin-bottom: 20px;
            }
          }
      }
    }
  }
}
@media (max-width: 1120px) {
  .wrapper {
    .subscribe {
      &__content {
        margin-top: 160px;
      }
    }
  }
}
@media (max-width: 1050px) {
  .wrapper {
    .subscribe {
      &__content {
        &__title, h4 {
          font-size: 1.8rem;
        }
        &__subtitle {
          margin: 10px 0 10px 0;
          font-size: 4rem;
        }
        p {
          font-size: 1.6rem;
        }
        &__submit {
          margin-top: 10px;
            input {
            margin-bottom: 10px;
            }
          }
      }
    }
  }
}
@media (max-width: 950px) {
  .wrapper {
    .subscribe {
      flex-direction: column;

      &__mobile {
        display: block;
        text-align: center;
        margin-top: 80px;

        &__title {
          font-family: 'Graphik-Medium';
          font-weight: 700;
          font-size: 2rem;
          line-height: 28px;
          letter-spacing: 0.1px;
          color: var(--text-color);
        }
        &__subtitle {
          margin: 17px 0 25px 0;
          font-family: 'Graphik-Regular';
          font-weight: 400;
          font-size: 4.8rem;
          line-height: 55px;
          letter-spacing: 0.2px;
          color: var(--text-color);
        }
        p {
          margin-top: 5px;
          font-family: 'Graphik-Light';
          font-weight: 400;
          font-size: 2.8rem;
          line-height: 40px;
          letter-spacing: 0.2px;
          color: #374754;
        }
      }

      &__image {
        width: 100%;
        margin-top: 59px;
      }
      &__content {
        width: 100%;
        margin-top: 59px;
        text-align: center;

        &__title, &__subtitle {
          display: none;
        }

        &__submit {
          margin-top: 34px;
          input, .btn {
            display: block;
            width: 100%;
          }
        }
      }
    }
  }
}
</style>
