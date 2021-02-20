<template>
  <div class="editorialPage">
    <Wrapper>
      <div class="editorialPage__content">
        <Steps class="steps__mobile" />

        <div class="editorialPage__hero">
          <h3 class="editorialPage__hero__header">
            Maak kans op een €1000 waardebon!
          </h3>

          <div class="editorialPage__hero__imgMobile" />

          <div class="editorialPage__hero__imgDesktopWrapper">
            <img class="editorialPage__hero__imgDesktop" src="../assets/desktop/editorialHero.svg" />

            <img class="editorialPage__hero__awards" src="../assets/desktop/awardsAvailable.svg" />
          </div>
        </div>

        <div class="editorialPage__form">
          <Form v-on:FORM_SUBMITTED="$emit('FORM_SUBMITTED')" />
        </div>

        <div class="editorialPage__footerHero" />
      </div>

      <Footer />
    </Wrapper>
  </div>
</template>

<script>
import Footer from '../components/Footer';
import Steps from '../components/Steps';
import Form from '../components/RegisterForm';
import Wrapper from './Wrapper';

export default {
  name: 'EditorialPage',

  components: {
    Footer,
    Steps,
    Wrapper,
    Form,
  },
}
</script>

<style style="scss" scoped>
.editorialPage {
  width: 100vw;
  min-height: 100vh;
  box-sizing: border-box;
  background: rgb(72,100,205);
  background: linear-gradient(0deg, rgba(72,100,205,1) 0%, rgba(0,153,255,1) 100%);
}

.steps__desktop {
  display: none;
}

.editorialPage__hero {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  padding: 24px 0;
}

.editorialPage__hero__header {
  width: 60%;
  font-size: 26px;
  font-weight: bold;
  line-height: 31px;
  color: #fff;
}

.editorialPage__hero__imgMobile {
  width: 102px;
  height: 130px;
  background: url('../assets/awardsAvailable.svg');
  background-repeat: no-repeat;
  background-size: cover;
}

.editorialPage__form {
  padding: 32px 16px;
  margin: 0 16px;
  background: rgba(255, 255 , 255, .1);
  border-radius: 6px;
  color: #fff;
  text-align: center;
}

.editorialPage__footerHero {
  width: 257px;
  height: 257px;
  background: url('../assets/footerHero.svg');
  margin: 24px auto;
}

.editorialPage__hero__imgDesktopWrapper {
  display: none;
}

/** Desktop styles */
@media only screen and (min-width: 768px) {
  .editorialPage__content {
    display: flex;
    padding: 80px 0;
  }

  .steps__mobile {
    display: none;
  }

  .editorialPage__footerHero {
    display: none;
  }

  .steps__desktop {
    display: flex;
    justify-content: space-between;
    padding: 14px 0;
  }

  .editorialPage__hero__imgDesktopWrapper {
    display: block;
    width: 100%;
    height: 0;
    padding-top: 100%;
    position: relative;
  }

  .editorialPage__hero__imgDesktop {
    position: absolute;
    top: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .editorialPage__hero__awards {
    position: absolute;
    top: 25%;
    right: 30px;
    width: 32%;
  }

  .editorialPage__hero__imgMobile {
    display: none;
  }

  .editorialPage__hero {
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    padding: 0;
    width: 60%;
  }

  .editorialPage__hero__header {
    width: 80%;
    font-size: 42px;
    text-align: center;
    line-height: 47px;
  }

  .editorialPage__form {
    padding: 16px 32px 24px 32px
  }
}
</style>
