<template>
  <div class="prizeItem">
    <div class="prizeItem__content">
      <img class="prizeItem__image__mobile" v-bind:src="getIamgeUrl()" />

      <div class="prizeItem__details">
        <div class="prizeItem__details_title">
          {{ title }}
        </div>

        <img class="prizeItem__image__desktop" v-bind:src="getIamgeUrl()" />

        <a class="prizeItem__details_link" v-bind:href="link">
          Kies deze >
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PrizeItem',

  methods: {
    getIamgeUrl() {
      const images = require.context('../assets/', false, /\.svg$/);

      return  images(`./${this.imageName}.svg`);
    }
  },

  props: {
    imageName: {
      type: String,
      required: true,
    },

    title: {
      type: String,
      required: true,
    },

    link: {
      type: String,
      required: true,
    },
  }
}
</script>

<style scoped>
.prizeItem {
  padding: 8px 16px;
}

.prizeItem__content {
  background: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 16px;
}

.prizeItem__image__mobile {
  display: inline-block;
  width: 97px;
  height: 90px;
  margin-right: 16px;
}

.prizeItem__details {
  display: flex;
  flex-direction: column;
  width: 50%;
}

.prizeItem__details_title {
  font-size: 16px;
  font-weight: 800;
  margin-bottom: 16px;
}

.prizeItem__details_link {
  color: #2B58BF;
  border: 1px solid #B4D1F8;
  font-size: 13px;
  text-align: center;
  padding: 8px 24px;
  text-decoration: none;
  border-radius: 25px;
}

.prizeItem__image__desktop {
  display: none;
}

/** Desktop styles */
@media only screen and (min-width: 768px) {
  .prizeItem {
    width: 33%;
    padding: 8px 24px 8px 0;
  }

  .prizeItem__content {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 331px;
    background: #fff;
  }

  .prizeItem:last-child {
    padding: 8px 0;
    width: calc(33% - 24px);
  }

  .prizeItem__image__mobile {
    display: none;
  }

  .prizeItem__image__desktop {
    display: block;
    width: 150px;
    height: 138px;
    margin: 0 auto 24px auto;
  }

  .prizeItem__details {
    text-align: center;
  }
}
</style>
