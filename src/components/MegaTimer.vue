<template>
  <div>
    <div class="container__timer">
      <div class="timer__title">Remaining&nbsp;time:</div>
      <div class="timer__main">
        {{ dateDiff.getDate() }}:{{
          dateDiff.getHours() < 10
            ? '0' + dateDiff.getHours()
            : dateDiff.getHours()
        }}:{{
          dateDiff.getMinutes() < 10
            ? '0' + dateDiff.getMinutes()
            : dateDiff.getMinutes()
        }}:{{
          dateDiff.getSeconds() < 10
            ? '0' + dateDiff.getSeconds()
            : dateDiff.getSeconds()
        }}
      </div>
      <div class="timer__bg"></div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const isMobile = ref(false);
    const dateNow = ref(Date.now());
    const dateDue = ref(new Date('2022-12-01T08:00:00'));
    const dateDiff = ref(new Date(dateDue.value - dateNow.value));
    let intervalUpdater = setInterval(() => {
      dateNow.value = Date.now();
      dateDiff.value = new Date(dateDue.value - dateNow.value);
      // console.log('tick');
      // if u want to add seconds use next string:
      // :{{ dateDiff.getSeconds() }}S
    }, 1000);

    return {
      isMobile,
      dateNow,
      dateDue,
      dateDiff,
      intervalUpdater,
    };
  },
};
</script>

<style lang="sass" scoped>
.container__timer
  position: relative
  display: flex
  flex-direction: column
  align-items: center
  justify-content: center
  width: 100%
  min-height: 120px
  gap: 44px
  z-index: 10
  .timer__title
    font-family: 'Montserrat'
    font-style: normal
    font-weight: 500
    font-size: 36px
    line-height: 22px
    text-transform: uppercase
    color: #FFFFFF
  .timer__main
    font-family: 'Montserrat'
    font-style: normal
    font-weight: 700
    font-size: 96px
    line-height: 22px
    text-transform: uppercase
    color: #FFFFFF
    text-shadow: 0px 4px 20px #000000
  .timer__bg
    display: none
    position: absolute
    background-image: url('/src/assets/bg_logo.png')
    background-size: cover
    background-position: center center
    background-repeat: no-repeat
    top: -55%
    min-width: 414px
    min-height: 257px
    z-index: -1
@media (max-width: 860px)
  .container__timer
    gap: 10px
    min-height: 100px
    .timer__title
      font-size: 12px !important
      line-height: 22px !important
    .timer__main
      font-size: 30px !important
      line-height: 22px !important
    .timer__bg
      display: block
</style>
