<template>
  <div>
    <div class="container__cards">
      <MegaSwiper
        v-if="isMobile"
        @requestRedirect="requestRedirect"
        :slides="dataArr"
      ></MegaSwiper>
      <div
        v-else
        @click="requestRedirect(el.link)"
        v-for="(el, id) in dataArr"
        :key="id"
        class="card__element"
      >
        <div class="el__text">
          {{ el.text }}
        </div>
        <img :src="el.imgHead" class="el__head" />
        <img :src="el.imgBody" class="el__body" />
      </div>
    </div>
    <div class="bottom__deco"></div>
  </div>
</template>

<script>
import MegaSwiper from './MegaSwiper.vue';
import list_top_1 from '../assets/list/list_top_1.png';
import list_top_2 from '../assets/list/list_top_2.png';
import list_top_3 from '../assets/list/list_top_3.png';
import list_top_4 from '../assets/list/list_top_4.png';
import list_top_5 from '../assets/list/list_top_5.png';
import list_top_6 from '../assets/list/list_top_6.png';
import list_top_7 from '../assets/list/list_top_7.png';
import list_top_8 from '../assets/list/list_top_8.png';
import list_top_9 from '../assets/list/list_top_9.png';
import list_top_10 from '../assets/list/list_top_10.png';
import list_top_11 from '../assets/list/list_top_11.png';
import list_top_12 from '../assets/list/list_top_12.png';
import list_top_13 from '../assets/list/list_top_13.png';
import list_top_14 from '../assets/list/list_top_14.png';
import list_top_15 from '../assets/list/list_top_15.png';
import list_body_1 from '../assets/list/list_body_15.png';
import list_body_3 from '../assets/list/list_body_3.png';
import list_body_2 from '../assets/list/list_body_2.png';
import list_body_4 from '../assets/list/list_body_4.png';
import list_body_5 from '../assets/list/list_body_5.png';
import list_body_6 from '../assets/list/list_body_6.png';
import list_body_7 from '../assets/list/list_body_7.png';
import list_body_8 from '../assets/list/list_body_8.png';
import list_body_9 from '../assets/list/list_body_9.png';
import list_body_10 from '../assets/list/list_body_10.png';
import list_body_11 from '../assets/list/list_body_11.png';
import list_body_12 from '../assets/list/list_body_12.png';
import list_body_13 from '../assets/list/list_body_13.png';
import list_body_14 from '../assets/list/list_body_14.png';
import list_body_15 from '../assets/list/list_body_15.png';
import { ref, watchEffect } from 'vue';
export default {
  setup(props, { emit }) {
    const dataArr = [
      {
        imgHead: list_top_1,
        imgBody: list_body_1,
        text: 'first deposit',
        link: 'https://megapari.com/bonus/rules/1st',
      },
      {
        imgHead: list_top_2,
        imgBody: list_body_2,
        text: '1500€ + 150FS',
        link: 'https://megapari.com/bonus/rules/slot_first_deposit',
      },
      {
        imgHead: list_top_3,
        imgBody: list_body_3,
        text: 'Special tournament',
        link: 'https://megapari.com/line/football/1938952-fifa-world-cup-2022',
      },
      {
        imgHead: list_top_4,
        imgBody: list_body_4,
        text: 'black friday tournament',
        link: 'https://megapari.com/ru/bonus/rules/drops_and_wins_2022',
      },
      {
        imgHead: list_top_5,
        imgBody: list_body_5,
        text: 'get +10% to winning',
        link: 'https://megapari.com/',
      },
      {
        imgHead: list_top_6,
        imgBody: list_body_6,
        text: 'SATURDAY BONUS ',
        link: 'https://megapari.com/bonus/rules/saturday_football_bonus',
      },
      {
        imgHead: list_top_7,
        imgBody: list_body_7,
        text: 'Cashback up to 30% for eSports',
        link: 'https://megapari.com/cybercalendar',
      },
      {
        imgHead: list_top_8,
        imgBody: list_body_8,
        text: ' 5% cashback',
        link: 'https://megapari.com/allgamesentrance',
      },
      {
        imgHead: list_top_9,
        imgBody: list_body_9,
        text: 'Catch your wished odds',
        link: 'https://megapari.com/',
      },
      {
        imgHead: list_top_10,
        imgBody: list_body_10,
        text: 'jackpot ',
        link: 'https://megapari.com/toto/fifteen',
      },
      {
        imgHead: list_top_11,
        imgBody: list_body_11,
        text: 'bet with zero balance ',
        link: 'https://megapari.com/bonus/rules/doverie',
      },
      {
        imgHead: list_top_12,
        imgBody: list_body_12,
        text: 'Prize Pool €500 000',
        link: 'https://megapari.com/bonus/rules/grand_holidays_tournament',
      },
      {
        imgHead: list_top_13,
        imgBody: list_body_13,
        text: 'cashout',
        link: 'https://megapari.com/',
      },
      {
        imgHead: list_top_14,
        imgBody: list_body_14,
        text: 'weekly 3% real money',
        link: 'https://megapari.com/bonus/rules/cash',
      },
      {
        imgHead: list_top_15,
        imgBody: list_body_15,
        text: 'refund bet loss',
        link: 'https://megapari.com/',
      },
    ];
    const isMobile = ref(false);
    watchEffect(() => {
      if (window.screen.width <= 860) {
        isMobile.value = true;
      } else {
        isMobile.value = false;
      }
    });
    const requestRedirect = (where) => {
      emit('requestRedirect', where);
    };
    return {
      dataArr,
      isMobile,
      requestRedirect,
    };
  },
  components: { MegaSwiper },
};
</script>

<style lang="sass" scoped>
.container__cards
  display: flex
  flex-direction: row
  flex-wrap: wrap
  align-items: center
  justify-content: center
  gap: 15px
  max-width: 1200px
  margin: 0 auto
  z-index: 10
  .card__element
    position: relative
    display: flex
    align-items: flex-end
    justify-content: flex-start
    height: 148px
    min-width: 286px
    max-width: 290px
    padding: 20px
    background: radial-gradient(50% 50% at 50% 50%, rgba(89, 89, 89, 0.2) 0%, rgba(0, 0, 0, 0) 100%), #171717
    border-radius: 32px
    cursor: pointer
    &:nth-child(2) .el__text
      max-width: 55px
      text-align: center
    &:nth-child(4) .el__text
      max-width: 122px
    &:nth-child(5) .el__text
      max-width: 100px
    &:nth-child(7) .el__text
      max-width: 70px
    &:nth-child(8) .el__text
      max-width: 120px
      margin-bottom: 10%
    &:nth-child(10) .el__text
      max-width: 120px
      margin-bottom: 10%
    &:nth-child(11) .el__text
      max-width: 130px
      margin-bottom: 5%
    &:nth-child(12) .el__text
      margin-bottom: 5%
    &:nth-child(13) .el__text
      max-width: 130px
      margin-bottom: 10%
    &:nth-child(14) .el__text
      max-width: 130px
      margin-bottom: 5%
    &:nth-child(15) .el__text
      max-width: 80px
      margin-bottom: 5%
    &:nth-child(1) .el__body
      bottom: unset
      right: 0
    &:nth-child(3) .el__body
      // bottom: unset
      right: 0
    &:nth-child(14) .el__body
      // bottom: unset
      right: 0
    &:nth-child(15) .el__body
      bottom: unset
      right: 0
    .el__text
      font-family: 'Montserrat'
      font-style: normal
      font-weight: 700
      font-size: 15px
      line-height: 15px
      max-width: 110px
      text-transform: uppercase
      color: #FFFFFF
    .el__head
      position: absolute
      top: -12px
      left: -14px
    .el__body
      position: absolute
      right: -5%
      bottom: 0
.bottom__deco
  position: absolute
  bottom: 26px
  left: calc(50% - calc(1712px/2))
  background-image: url(/src/assets/bg_bottom.png)
  background-size: contain
  background-position: center
  background-repeat: no-repeat
  min-width: 1714px
  height: 1072px
  z-index: -1
@media (max-width: 860px)
.bottom__deco
  // position: sticky
  background-repeat: repeat
</style>
