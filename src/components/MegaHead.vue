<template>
  <div class="container__header">
    <div class="header__banner">
      <img
        @click="requestRedirect"
        src="../assets/banner_title.svg"
        class="banner__title"
      />
      <div class="banner__text">150% DEPOSIT BONUS</div>
      <div class="banner__text__small">up to 300 EUR</div>
      <div @click="requestRedirect" class="banner__btn">
        get&nbsp;your&nbsp;bonus
      </div>
    </div>
    <div @click.stop="requestRedirect" class="bf__logo">
      <div class="bf__bg"></div>
    </div>
  </div>
</template>

<script>
export default {
  setup(props, { emit }) {
    const requestRedirect = () => {
      const mainLink = 'https://megapari.com/information/payment';
      emit('requestRedirect', mainLink);
    };
    return {
      requestRedirect,
    };
  },
};
</script>

<style lang="sass" scoped>
.container__header
  display: flex
  flex-direction: row
  align-items: center
  justify-content: center
  gap: 250px
  width: 100%
  padding: 180px 120px
  padding-bottom: 0
  .header__banner
    display: flex
    flex-direction: column
    align-items: center
    gap: 20px
    z-index: 20
    .banner__title
      height: 37px
      width: 322px
      cursor: pointer
    .banner__text
      font-family: 'Montserrat'
      font-style: normal
      font-weight: 700
      font-size: 48px
      line-height: 48px
      text-align: center
      text-transform: uppercase
      color: #FFFFFF
      max-width: 370px
    .banner__text__small
      font-family: 'Montserrat'
      font-style: normal
      font-weight: 500
      font-size: 36px
      line-height: 22px
      text-align: center
      text-transform: uppercase
      color: #FFFFFF
    .banner__btn
      margin-top: 50px
      font-family: 'Montserrat'
      font-style: normal
      font-weight: 700
      font-size: 16px
      line-height: 22px
      text-transform: uppercase
      color: #000000
      background: linear-gradient(177.69deg, #FFC700 1.94%, rgba(255, 199, 0, 0) 130.51%), #FFF500
      border-radius: 11px
      padding: 17px 45px
      cursor: pointer
  .bf__logo
    position: relative
    min-width: 434px
    height: 303px
    background-image: url('/src/assets/bf_logo.svg')
    background-size: cover
    background-position: center center
    background-repeat: no-repeat
    z-index: 1
    cursor: pointer
    .bf__bg
      position: absolute
      top: -209px
      left: -350px
      width: 1133px
      height: 702px
      background-image: url('/src/assets/bg_logo.png')
      background-size: contain
      background-position: center
      background-repeat: no-repeat
      cursor: default
@media (max-width: 860px)
  .container__header
    // flex-direction: column
    gap: 49px
    padding: 20px 25px
    padding-bottom: 0
    .header__banner
      gap: 10px
      .banner__title
        max-width: 112px
        max-height: 13px
      .banner__text
        font-size: 20px !important
        line-height: 22px !important
        max-width: 120px
      .banner__text__small
        font-size: 15px !important
        line-height: 22px !important
        min-width: 120px
      .banner__btn
        padding: 8px 10px
        margin-top: 0px
    .bf__logo
      min-width: 131px
      min-height: 91px
      max-width: 131px
      max-height: 91px
      .bf__bg
        display: none
</style>
