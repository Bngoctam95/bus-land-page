<template>
  <div class="wrapper">
    <div class="contact">
      <div class="contact__heading">
        <h2>Contact Us</h2>
        <p>
          Most calendars are designed for teams.<br>
          <span>Slate is designed for freelancers</span>
        </p>
      </div>
      <div class="contact__content">
        <div class="contact__content__form">
          <div class="heading">
            <h2>Contact Us</h2>
          </div>
          <div class="input-container">
            <input id="name" v-model="name" class="input" type="text" placeholder="Your Name">
          </div>
          <div class="input-container">
            <input id="mail" v-model="email" class="input" type="mail" placeholder="Your Email">
          </div>
          <div class="textarea-container">
            <textarea id="message" v-model="message" class="textarea" placeholder="Your Message" />
          </div>
          <baseButton class="primary" @click="submitForm">
            Send
          </baseButton>
        </div>
        <div class="contact__content__map">
          <div class="infor">
            <div class="infor__item">
              <img src="@/static/images/map.svg" alt="">
              <p>
                6386 Spring St undefined Anchorage,<br>
                Georgia 12473 United States
              </p>
            </div>
            <div class="infor__item">
              <img src="@/static/images/phone.svg" alt="">
              <p>
                (843) 555-0130
              </p>
            </div>
            <div class="infor__item">
              <img src="@/static/images/mail.svg" alt="">
              <p>
                willie.jennings@example.com
              </p>
            </div>
          </div>
          <div class="map">
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d4559.238578375494!2d108.14936632061354!3d16.073407882189716!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3142195a82e5f72d%3A0xaeb067499b596847!2zRmFuY2FtcGluZyAtIETDoyBuZ2_huqFpIMSQw6AgTuG6tW5n!5e0!3m2!1svi!2s!4v1680592158666!5m2!1svi!2s"
              width="515"
              height="323"
              style="border:0;"
              allowfullscreen=""
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
            />
          </div>
          <div class="socials">
            <img src="@/static/images/twitter.svg" alt="">
            <img src="@/static/images/facebook.svg" alt="">
            <img src="@/static/images/linkedin.svg" alt="">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import baseButton from '@/components/button/base-button.vue'
export default {
  name: 'ContactUsSection',
  components: {
    baseButton
  },
  data () {
    return {
      email: '',
      name: '',
      message: '',
      user: []
    }
  },

  methods: {
    validateName () {
      if (this.name.length < 6) {
        alert('Nhập Name từ 6 ký tự trở lên')
        return false
      }
      return true
    },
    validateEmail () {
      const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
      if (!emailRegex.test(this.email)) {
        alert('Email không hợp lệ')
        return false
      }
      return true
    },
    submitForm () {
      if (!this.validateName()) {
        return true
      }
      if (!this.validateEmail()) {
        return true
      }
      const userObj = {
        name: this.name,
        email: this.email,
        message: this.message
      }
      this.user.push(userObj)

      this.name = ''
      this.email = ''
      this.message = ''
      alert('Đăng ký thành công!')
    }
  }
}
</script>

<style lang="scss" scoped>
  .wrapper {
    width: 100%;

    .contact {
      max-width: 1210px;
      width: 100%;
      margin: 0 auto;
      padding: 200px 0 100px 0;

      &__heading {
        text-align: center;
        font-weight: 400;
        letter-spacing: 0.2px;
        color: var(--text-color);

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

      &__content {
        display: flex;
        gap: 50px;
        margin-top: 50px;

        &__form {
          width: 453px;
          padding: 52px 50px;
          display: flex;
          flex-direction: column;
          align-items: flex-start;
          gap: 45px;
          background-color: white;
          box-sizing: border-box;
          border: 1px solid #DDDDDD;
          box-shadow: 0px 13px 19px rgba(0, 0, 0, 0.07);
          border-radius: 20px;

          .heading {
            width: 100%;
            font-family: 'Graphik-Medium';
            font-weight: 700;
            font-size: 2rem;
            text-align: center;
            line-height: 28px;
            letter-spacing: 0.1px;
            color: var(--text-color);
          }

          .input-container {
            height: 50px;
            position: relative;
            width: 100%;
          }

          .textarea-container {
            width: 353px;
            max-width: 100%;
            height: 193px;
          }

          .input, .textarea {
            padding: 10px 20px;
            font-family: 'Graphik-Light';
            font-weight: 400;
            font-size: 1.8rem;
            line-height: 16px;
            letter-spacing: 0.1px;
            background-color: #F5F5F5;
            border: 1px solid #E8E8E8;
            box-sizing: border-box;
            outline: 0;
          }

          .input {
            width: 100%;
            height: 100%;
            border-radius: 39px;
          }

          .textarea {
            width: 100%;
            height: 100%;
            resize: none;
          }
        }

        &__map {
          flex: 1;
          margin-top: 30px;

          .infor {
            display: grid;
            grid-template-columns: 30% 30% 30%;
            gap: 5%;
            text-align: center;
            &__item {
              img {
                margin-bottom: 10px;
              }
              p {
                font-weight: 400;
                font-size: 1.6rem;
                line-height: 23px;
                letter-spacing: 0.1px;
                color: var(--text-color);
              }
            }
          }

          .map {
            margin: 60px 0;
            text-align: center;
          }

          .socials {
            img {
              background-color: var(--primary-color);
              margin-right: 24px;
            }
          }
        }
      }
    }
  }

  /* Responsive */
  @media (max-width: 1050px) {
    .wrapper {
      .contact {
        padding: 200px 20px 100px 20px;
        &__content {
          &__form {
            width: 400px;
          }
          &__map {
            .infor {
               grid-template-columns: 35% 20% 35%;
              &__item {
                p {
                  font-size: 1.2rem;
                }
              }
            }
          }
        }
      }
    }
  }
  @media (max-width: 1000px) {
    .wrapper {
      .contact {

        &__content {
          flex-direction: column-reverse;
          align-items: center;

          &__map {
            width: 100%;
            display: flex;
            flex-direction: column-reverse;

            .infor {
              justify-content: space-evenly;
            }

            .map {
              display: none;
            }

            .socials {
              text-align: center;
              margin-bottom: 60px;
            }
          }
        }
      }
    }
  }

  @media (max-width: 800px) {
    .wrapper {
      .contact {

        &__content {

          &__map {

            .infor {
              margin: 0 auto;
              flex-direction: column;
              gap: 10px;

              &__item {
                display: flex;
                align-items: center;
                gap: 20px;

                img {
                  margin-bottom: 0;
                }

                p {
                  text-align: left;
                }
              }
            }
          }
        }
      }
    }
  }

  @media (max-width: 480px) {
    .wrapper {
      .contact {
        &__heading {
          padding: 0 20px;

          p {
            span {
              display: none;
            }
          }
        }
        &__content {
          padding-left: 5px;
          padding-right: 5px;
          &__form {
            width: 378px;
            max-width: 100%;
          }
          &__map {
            .infor {
              display: flex;
              flex-direction: column;
            }
          }
        }
      }
    }
  }
</style>
