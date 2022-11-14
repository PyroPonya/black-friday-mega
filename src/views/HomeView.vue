<template>
  <div class="container">
    <MegaHead @requestRedirect="redirectTo" class="m_head"></MegaHead>
    <MegaTimer class="m_timer"></MegaTimer>
    <MegaCards @requestRedirect="redirectTo" class="m_cards"></MegaCards>
  </div>
</template>

<script setup>
import MegaHead from '../components/MegaHead.vue';
import MegaTimer from '../components/MegaTimer.vue';
import MegaCards from '../components/MegaCards.vue';
const redirectTo = (where) => {
  window.location.assign(where);
  console.log(where);
};
</script>

<style lang="sass" scoped>
.container
  position: relative
  width: 100%
  height: 100%
  background-color: #000000
  overflow-x: hidden
  z-index: 0
  .m_timer
    width: 100%
    min-height: 120px
    margin-top: 120px
    margin-bottom: 120px
  .m_cards
    margin-bottom: 160px
    z-index: 10
@media (max-width: 860px)
  .m_timer
    margin-top: 80px
    margin-bottom: 80px
</style>
