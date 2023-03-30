<template>
  <div class="wrapper">
    <div class="features">
      <div class="features__title">
        <h2 class="features__title__label">
          Features
        </h2>
        <p class="features__title__content">
          Most calendars are designed for teams.<br>
          <span>Slate is designed for freelancers</span>
        </p>
      </div>
      <div class="features__mobile">
        <img class="features__mobile__video" src="@/static/images/features-imgmobile.png" alt="" title="Features images">
        <button class="features__mobile__btn">
          <img src="@/static/images/triangle.png" alt="">
        </button>
      </div>
      <ul class="features__list">
        <li
          v-for="(item, index) in featuresList"
          :key="index"
          class="features__item"
        >
          <img :src="require(`@/static/images/${item.icon}.svg`)" :alt="item.icon" :title="item.icon">
          <h4>{{ item.label }}</h4>
          <p>{{ item.content }}</p>
        </li>
      </ul>
      <div class="features__video">
        <img class="features__video__banner" src="@/static/images/features-images.png" alt="" title="Features images">
        <button class="features__video__btn">
          <img src="@/static/images/triangle.png" alt="">
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FeaturesSection',
  data () {
    return {
      featuresList: [
        {
          id: 1,
          icon: 'featuresIcon1',
          label: 'OpenType features Variable fonts',
          content: 'Slate helps you see how many more days you need to work to reach your financial goal.'
        },
        {
          id: 2,
          icon: 'featuresIcon3',
          label: 'Design with real data',
          content: 'Slate helps you see how many more days you need to work to reach your financial goal.'
        },
        {
          id: 1,
          icon: 'featuresIcon3',
          label: 'Fastest way to take action',
          content: 'Slate helps you see how many more days you need to work to reach your financial goal.'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  .wrapper {
    width: 100%;
    height: 1360px;

    & .features {
      width: 1210px;
      max-width: 100%;
      margin: 0 auto;

      &__title {
        margin-bottom: 80px;

        &__label {
          margin-bottom: 20px;
          font-size: 4.8rem;
          font-weight: 200;
          line-height: 55px;
          text-align: center;
          letter-spacing: 0.2px;
          color: #252B42;
        }

        &__content {
          font-weight: 400;
          font-size: 2.8rem;
          line-height: 40px;
          text-align: center;
          letter-spacing: 0.2px;
          color: #374754;
        }
      }

      &__list {
        width: 70%;
        display: flex;
        justify-content: space-between;
        gap: 20px;
        margin: 0 auto;
      }

      &__item {
        text-align: center;

        & img {
          width: 61px;
          height: 61px;
          margin-bottom: 15px;
        }

        & h4 {
          font-weight: 700;
          font-size: 2rem;
          line-height: 28px;
          text-align: center;
          letter-spacing: 0.1px;
          color: #252B42;
           margin-bottom: 10px;
        }

        & p {
          font-weight: 400;
          font-size: 1.8rem;
          line-height: 25px;
          text-align: center;
          letter-spacing: 0.2px;
          color: #374754;
        }
      }

      &__video {
        margin-top: 132px;
        position: relative;

        &__banner {
          width: 100%;
        }

        &__btn {
          width: 187px;
          height:187px;
          position: absolute;
          top: 50%;
          left: 50%;
          padding: 0;
          transform: translate(-50%, -50%);
          border-radius: 50%;
          border: none;
          cursor: pointer;
          background-color: var(--primary-color);
          box-shadow: 0px 5px 10px 0px rgba(0, 0, 0, 0.5);

          & img {
            position: absolute;
            top: 50%;
            left: 54%;
            transform: translate(-50%, -50%);
          }

          &:hover {
            background-color: #087ae3;
          }
        }
      }

      &__mobile {
        display: none;
      }
    }
  }

  /* Responsive */
  @media (max-width: 880px) {
    .wrapper {
      & .features {
        &__list {
          flex-direction: column;
        }

        &__video {
          margin-top: 80px;

          &__btn {
            width: 150px;
            height:150px;
          }
        }
      }
    }
  }

  @media (max-width: 576px) {
    .wrapper {
      & .features {
        &__title {
          margin-bottom: 50px;
          &__content {
            padding: 0 55px;
            & span {
              display: none;
            }
          }
        }

        &__list {
          margin-top: 30px;
        }

        &__item {
          margin-bottom: 40px;
        }

        &__video {
          display: none;
        }

        &__mobile {
          display: block;
          position: relative;

          &__video {
            width: 100%;
          }

          &__btn {
            width: 80px;
            height:80px;
            position: absolute;
            top: 50%;
            left: 50%;
            padding: 0;
            transform: translate(-50%, -50%);
            border-radius: 50%;
            border: none;
            cursor: pointer;
            background-color: var(--primary-color);
            box-shadow: 0px 5px 10px 0px rgba(0, 0, 0, 0.5);

            & img {
              width: 25px;
              height:25px;
              position: absolute;
              top: 50%;
              left: 54%;
              transform: translate(-50%, -50%);
            }

            &:hover {
              background-color: #087ae3;
            }
          }
        }
      }
    }
  }
</style>
