<template>
  <div class="wrapper">
    <div class="partners">
      <div class="partners__content">
        <h2>Partners</h2>
        <p>
          Most calendars are designed for teams.<br>
          Slate is designed for freelancers
        </p>
      </div>
      <ul class="partners__list">
        <li
          v-for="(item, index) in partnerList"
          :key="index"
          class="partners__item"
        >
          <h4 class="partners__item__name">
            {{ item.clientName }}
          </h4>
          <img :src="require(`@/static/images/${item.logo}`)" alt="">
        </li>
      </ul>
      <baseButton class="primary partners__btn">
        Try For Free
      </baseButton>
    </div>
  </div>
</template>

<script>
import baseButton from '@/components/button/base-button.vue'
export default {
  name: 'PartnersSection',
  components: {
    baseButton
  },
  data () {
    return {
      partnerList: [
        {
          id: 1,
          clientName: 'google',
          logo: 'google.png'
        },
        {
          id: 2,
          clientName: 'uber',
          logo: 'uber.png'
        },
        {
          id: 3,
          clientName: 'dropbox',
          logo: 'dropbox.png'
        },
        {
          id: 4,
          clientName: 'microsoft',
          logo: 'microsoft.png'
        },
        {
          id: 5,
          clientName: 'amazon',
          logo: 'amazon.png'
        },
        {
          id: 6,
          clientName: 'amazon1',
          logo: 'amazon.png'
        },
        {
          id: 7,
          clientName: 'amazon2',
          logo: 'amazon.png'
        },
        {
          id: 8,
          clientName: 'amazon3',
          logo: 'amazon.png'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
  .wrapper {
    width: 100%;
    .partners {
      max-width: 1210px;
      width: 100%;
      margin: 0 auto;
      padding: 130px 0 80px 0;

      &__content {
        margin-bottom: 80px;
        color: var(--text-color);
        font-family: 'Graphik-Light';
        font-weight: 400;
        text-align: center;
        letter-spacing: 0.2px;
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

      &__list {
        margin-bottom: 80px;
        padding: 0 20px;
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-gap: 20px;
      }

      &__item {
        padding-top: 30px;
        font-family: 'Graphik-Light';
        text-transform: capitalize;
        text-align: center;
        font-weight: 400;
        font-size: 1.6rem;
        line-height: 23px;
        letter-spacing: 0.1px;
        color: #374754;
        box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;

        &__name {
          margin-bottom: 15px;
        }

        img {
          margin-bottom: 32px;
          padding: 0 20px;
        }
      }

      &__btn {
        display: block;
        margin: 0 auto;
      }
    }
  }

  /* Responsive */
@media (max-width: 1250px) {
  .wrapper {
    .partners {

      &__list {
        grid-template-columns: repeat(3, 1fr);
      }
    }
  }
}
@media (max-width: 950px) {
  .wrapper {
    .partners {
      padding: 60px 0 50px 0;
      &__list {
        grid-template-columns: repeat(1, 1fr);
        padding: 0 70px;
      }
    }
  }
}
@media (max-width: 500px) {
  .wrapper {
    .partners {
      &__content {
        padding: 0 30px;
      }
      &__item {
        img {
          width: 193px;
        }
      }
    }
  }
}
</style>
