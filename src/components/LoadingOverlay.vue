<template>
  <div class="loadingOverlay" v-animate-css="animation">
    <h3 class="loadingOverlay__header">
      Wacht aub even
    </h3>

    <p class="loadingOverlay__details">
      Jouw antwoorden worden gecontroleerd...
    </p>

    <BeatLoader :size="'12px'" :loading="true" :color="'#fff'" />

    <div class="loadingOverlay__uspsList">
      <div v-for="(usp, index) in usps" :key="index" class="loadingOverlay__usp">
        <div class="loadingOverlay__usp__icon" />

        <div class="loadingOverlay__usp__text">
          {{ usp }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BeatLoader from 'vue-spinner/src/BeatLoader.vue';

export default {
  name: 'LaodingOverlay',

  components: {
    BeatLoader,
  },

  data() {
    return {
      usps: [
        'Alle antworden ontvangen',
        'Geen dubbele registraties gevonden',
        'Gefeliciteerd, je komt in annmerking!',
      ],
      animation: {
        classes: 'flipInY',
        delay: 0,
        duration: 500,
      }
    }
  },
}
</script>

<style scoped>
  .loadingOverlay {
    position: fixed;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 100vw;
    height: 100vh;
    background: rgba(0, 0, 0, .7);
  }

  .loadingOverlay__header {
    color: #11AEF4;
    font-size: 34px;
    font-weight: bold;
    margin-bottom: 18px;
  }

  .loadingOverlay__details {
    padding: 0 40px;
    color: #fff;
    text-align: center;
    font-size: 20px;
  }

  .loadingOverlay__uspsList {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 18px;
  }

  .loadingOverlay__usp {
    display: flex;
    align-items: center;
    font-size: 16px;
    margin-bottom: 12px;

  }

  .loadingOverlay__usp__icon {
    width: 20px;
    height: 20px;
    margin-right: 8px;
    background: url('../assets/icons/checkmarkBlue.svg');
  }

  .loadingOverlay__usp__text {
    color: #fff;
    font-weight: 400;
  }

  /** Desktop styles */
  @media only screen and (min-width: 768px) {
    .loadingOverlay__header {
      font-size: 37px;
    }

    .loadingOverlay__details {
      font-size: 26px;
    }
  }

</style>
