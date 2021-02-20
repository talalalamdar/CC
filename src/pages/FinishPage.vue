<template>
  <div class="finishPage">
    <div class="finishPage__header">
      <div class="finishPage__header__text">
        Bedankt voor je deelname
      </div>

      <div class="finishPage__header__image"/>
    </div>

    <Wrapper>
      <div class="finishPage__prizesList">
        <div class="prizesList__header">
          <div class="prizesList__header_title">
            Dankjewel. Selecteer hier je prijs!
          </div>

          <span class="prizesList__header_time">
            Tijd over 06:25:38
          </span>
        </div>

        <div class="prizesList">
          <PrizeItem
            v-for="(item, index) in prizesItems"
            v-bind:key="index"
            v-bind:imageName="item.image"
            v-bind:title="item.title"
            v-bind:link="item.link"
          />
        </div>

        <div class="banner">
          <div class="banner_arrow" />
            Recentelijk verlopen aanbiedingen
          <div class="banner_arrow" />
        </div>

        <div class="recentPrizesList">
          <RecentPrize
            v-for="(item, index) in recentPrizes"
            v-bind:key="index"
            v-bind:imageName="item.image"
            v-bind:title="item.title"
            v-bind:endDate="item.endDate"
            v-bind:link="item.link"
          />
        </div>
      </div>

      <Footer textColor="#000" />
    </Wrapper>
  </div>
</template>

<script>
import PrizeItem from '../components/PrizeItem.vue';
import RecentPrize from '../components/RecentPrize.vue';
import Footer from '../components/Footer.vue';
import Wrapper from './Wrapper.vue';

export default {
  name: 'FinishPage',

  components: {
    PrizeItem,
    RecentPrize,
    Footer,
    Wrapper,
  },

  data() {
    return {
      prizesItems: [
        {
          image: 'awardsPrizeItem-1',
          title: 'Maak kans op een $1000 Waardebon!',
          link: '#',
        },
        {
          image: 'iphonePrizeItem',
          title: 'Win een IPhone 12 Pro',
          link: '#',
        },
        {
          image: 'awardsPrizeItem-2',
          title: 'Maak kans op een $1000 Waardebon!',
          link: '#',
        },
      ],

      recentPrizes: [
        {
          image: 'recentPrize-2',
          title: 'Maak kans op een $1000 Waardebon!',
          endDate: '03-06-2020',
          link: '#',
        },
        {
          image: 'recentPrize',
          title: 'Maak kans op een $1000 Waardebon!',
          endDate: '03-07-2020',
          link: '#',
        },
        {
          image: 'recentPrize-2',
          title: 'Maak kans op een $1000 Waardebon!',
          endDate: '03-08-2020',
          link: '#',
        },
        {
          image: 'recentPrize',
          title: 'Maak kans op een $1000 Waardebon!',
          endDate: '03-09-2020',
          link: '#',
        },
      ]
    }
  }
}
</script>

<style scoped>
.finishPage {
  width: 100vw;
  min-height: 100vh;
  box-sizing: border-box;
  background: #FEFAF6;
}

.finishPage__header {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  padding: 24px;
  background: rgb(255,233,93);
  background: linear-gradient(150deg, rgba(255,233,93,1) 0%, rgba(248,100,45,1) 100%);
  color: #fff;
}

.finishPage__header__text {
  max-width: 60%;
  font-size: 28px;
  font-weight: bold;
  margin-right: 18px;
}

.finishPage__header__image {
  width: 91px;
  height: 91px;
  background: url('../assets//giftImage.svg');
  background-position: center;
  background-size: cover;
}

.prizesList__header {
  display: flex;
  align-items: center;
  flex-direction: column-reverse;
  text-align: center;
  justify-content: flex-end;
  padding: 16px 36px;
}

.prizesList__header_time {
  font-size: 16px 24px;
}

.prizesList__header_title {
  font-size: 22px;
  font-weight: bold;
}

.banner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  white-space: nowrap;
  margin: 24px 16px;
  padding: 16px;
  background: #F44336;
  color: #fff;
}

.banner_arrow {
  width: 10px;
  height: 10px;
  background: url('../assets/icons/arrowDoubleBottom.svg');
  background-size: cover;
  background-position: center;
}

.recentPrizesList {
  margin: 8px 16px 32px 16px;
}

/** Desktop styles */
@media screen and (min-width: 768px) {
  .finishPage__header__text {
    margin-right: 32px;
  }

  .prizesList__header {
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    flex-direction: row;
    padding: 16px 0;
  }


  .prizesList__header_time {
    text-align: right;
    width: 32%;
  }

  .prizesList {
    display: flex;
    justify-content: space-between;
  }

  .banner {
    margin: 24px 0;
  }

  .recentPrizesList {
    display: flex;
    justify-content: space-between;
    margin: 8px 0 32px 0;
  }
}
</style>
