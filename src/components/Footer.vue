<template>
  <div class="footer" v-bind:style="{ color: textColor }">
    <div class="footer__statement">
      Deze promotie wordt onafhankelijk georganiseerd door Green Flamingo, en heeft op geen enkele manier een relatie met de fabrikanten van de getoonde producten. De handelsmerken zijn het eigendom van hun respectievelijke eigenaren. Alle afbeeldingen worden alleen getoond voor illustratieve doeleinden. Deelname mogelijk tot 31-12-2020.
    </div>

    <div class="footer__navigation">
      <a href="#" class="footer__navigation__item">
        VoorWaarden
      </a>

      <a href="#" class="footer__navigation__item">
        Privacy
      </a>

      <a href="#" class="footer__navigation__item">
        GDPR Transparency
      </a>

      <a href="#" class="footer__navigation__item">
        Cookies
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Footer',

  props: {
    textColor: {
      type: String,
      default: 'white'
    }
  }
}
</script>

<style scoped>
  .footer {
    padding: 0 16px 42px 16px;
    text-align: center;
    font-size: 11px;
    line-height: 15px;
    color: #fff;
  }

  .footer__navigation {
    display: flex;
    justify-content: space-evenly;
    margin-top: 16px;
  }

  .footer__navigation__item {
    color: inherit !important;
    text-decoration: none;
  }

  /** Desktop styles */
  @media only screen and (min-width: 768px) {
    .footer__navigation {
      width: 50%;
      margin: 16px auto 0 auto;
    }
  }
</style>
