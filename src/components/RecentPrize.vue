<template>
  <div class="recentPrize">
    <a v-bind:href="link" class="recentPrize__content">
      <div class="recentPrize__imageWrapper">
        <img class="recentPrize__image" v-bind:src="getIamgeUrl()" />

        <div class="recentPrize__date">
          Verlopen op {{ endDate }}
        </div>
      </div>

      <div class="recentPrize__details">
        <div class="recentPrize__details_title">
          {{ title }}
        </div>
      </div>
    </a>
  </div>
</template>

<script>
export default {
  name: 'recentPrize',

  methods: {
    getIamgeUrl() {
      const images = require.context('../assets', false, /\.svg$/);

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

    endDate: {
      type: String,
      required: true,
    }
  }
}
</script>

<style scoped>
.recentPrize__content {
  display: flex;
  justify-content: center;
  align-items: center;
  background: #fff;
  margin: 8px 0;
  padding: 16px;
  text-decoration: none;
  color: #000;
}

.recentPrize__date {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  right: 12px;
  top: 35px;
  padding: 8px 14px;
  background: #F44336;
  color: #fff;
  border-radius: 20px;
  font-size: 8px;
  white-space: nowrap;
}

.recentPrize__imageWrapper {
  position: relative;
}

.recentPrize__image {
  width: 97px;
  height: 90px;
  margin-right: 24px;
}

.recentPrize__details {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 50%;
}

.recentPrize__details_title {
  font-size: 14px;
  font-weight: 700;
}

.recentPrize__details_link {
  color: #2B58BF;
  border: 1px solid #B4D1F8;
  font-size: 13px;
  text-align: center;
  padding: 8px 24px;
  text-decoration: none;
  border-radius: 25px;
}

/** Desktop styles */
@media only screen and (min-width: 768px) {
  .recentPrize {
    width: 25%;
    padding-right: 24px;
  }

  .recentPrize:last-child {
    width: calc(25% - 24px);
    padding-right: 0;
  }

  .recentPrize__content {
    flex-direction: column-reverse;
    padding: 24px;
  }

  .recentPrize__image {
    width: 146px;
    height: 102px;
    margin: 0;
  }

  .recentPrize__date {
    right: -23px;
    font-size: 13px;
    padding: 10px 16px;
  }

  .recentPrize__details_title {
    text-align: center;
  }
}
</style>
