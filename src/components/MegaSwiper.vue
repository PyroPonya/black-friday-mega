<template>
  <swiper
    :slidesPerView="1"
    :spaceBetween="55"
    :freeMode="false"
    :autoplay="{
      delay: 3000,
      disableOnInteraction: false,
    }"
    :rewind="true"
    :navigation="true"
    :pagination="false"
    :modules="modules"
    class="mySwiper"
  >
    <swiper-slide v-for="(el, id) in slides" :key="id" class="swiper__slide">
      <div @click="requestRedirect(el.link)" class="card__element">
        <div class="el__text">{{ el.text }}</div>
        <img :src="el.imgHead_mobile" class="el__head" />
        <img :src="el.imgBody_mobile" class="el__body" />
      </div>
    </swiper-slide>
  </swiper>
</template>
<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Navigation } from 'swiper';

// Import Swiper styles
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/free-mode';
import 'swiper/css/pagination';

// import required modules
import { FreeMode, Pagination } from 'swiper';

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  props: ['slides'],
  setup(props, { emit }) {
    const requestRedirect = (where) => {
      emit('requestRedirect', where);
    };
    return {
      modules: [FreeMode, Pagination, Navigation],
      props,
      requestRedirect,
    };
  },
};
</script>
<style scoped>
.swiper {
  width: 100%;
  height: 100%;
}

.swiper-slide {
  text-align: center;
  font-size: 18px;
  background: none;
  min-height: 390px;
  /* max-width: 288px !important; */
  min-width: 287px !important;
  /* width: 288px !important; */

  /* Center slide text vertically */
  display: -webkit-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  -webkit-justify-content: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  -webkit-align-items: center;
  align-items: center;
}

.card__element {
  position: relative;
  display: flex;
  align-items: flex-start;
  justify-content: center;
  height: 255px;
  min-width: 286px;
  max-width: 290px;
  padding: 20px;
  padding-top: 80px;
  background: radial-gradient(
      50% 50% at 50% 50%,
      rgba(147, 147, 147, 0.5) 0%,
      rgba(0, 0, 0, 0) 100%
    ),
    #171717;
  border-radius: 32px;
  cursor: pointer;
}
.swiper__slide:nth-child(1) .el__text {
  max-width: 155px;
  margin-top: -5%;
}
.swiper__slide:nth-child(1) .el__body {
  bottom: 20px;
  width: 155px;
  height: 94px;
}
.swiper__slide:nth-child(2) .el__text {
  max-width: 140px;
}
.swiper__slide:nth-child(2) .el__body {
  width: 186px;
  height: 137px;
}
.swiper__slide:nth-child(3) .el__body {
  max-height: 135px;
  /* bottom: -10px; */
}
.swiper__slide:nth-child(4) .card__element {
  align-items: flex-end;
  justify-content: flex-start;
}
.swiper__slide:nth-child(4) .el__text {
  max-width: 55px;
}
.swiper__slide:nth-child(4) .el__body {
  top: 0px;
  right: -20px;
}
.swiper__slide:nth-child(5) .card__element {
  align-items: flex-end;
  justify-content: center;
}
.swiper__slide:nth-child(5) .el__text {
  max-width: 138px;
}
.swiper__slide:nth-child(5) .el__body {
  bottom: 60px;
  height: 144px;
  width: 148px;
}
.swiper__slide:nth-child(6) .el__text {
  max-width: 128px;
  margin-top: -10px;
}
.swiper__slide:nth-child(6) .el__body {
  width: 168px;
  height: 164px;
}
.swiper__slide:nth-child(7) .el__text {
  max-width: 148px;
  margin-top: -15px;
}
.swiper__slide:nth-child(7) .el__body {
  width: 188px;
  height: 131px;
}
.swiper__slide:nth-child(8) .el__text {
  max-width: 230px;
}
.swiper__slide:nth-child(8) .el__body {
  width: 145px;
  height: 148px;
}
.swiper__slide:nth-child(9) .el__text {
  max-width: 230px;
  margin-top: -15px;
}
.swiper__slide:nth-child(9) .el__body {
  width: 184px;
  height: 152px;
}
.swiper__slide:nth-child(10) .card__element {
  display: flex;
  justify-content: center;
  align-items: flex-end;
}
.swiper__slide:nth-child(10) .el__body {
  bottom: 50px;
  width: 92px;
  height: 133px;
}
.swiper__slide:nth-child(11) .el__text {
  max-width: 170px;
  margin-top: -10px;
}
.swiper__slide:nth-child(11) .el__body {
  width: 87px;
  height: 121px;
  margin-bottom: 10px;
}
.swiper__slide:nth-child(12) .el__text {
  max-width: 170px;
  margin-top: -10px;
}
.swiper__slide:nth-child(12) .el__body {
  width: 154px;
  height: 153px;
}
.swiper__slide:nth-child(13) .card__element {
  display: flex;
  justify-content: center;
  align-items: flex-end;
}
.swiper__slide:nth-child(13) .el__body {
  bottom: 60px;
  width: 105px;
  height: 113px;
}
.swiper__slide:nth-child(13) .el__text {
  max-width: 130px;
}
.swiper__slide:nth-child(14) .el__text {
  max-width: 150px;
  margin-top: -10px;
}
.swiper__slide:nth-child(14) .el__body {
  width: 155px;
  height: 148px;
}
.swiper__slide:nth-child(15) .el__text {
  max-width: 106px;
}
.swiper__slide:nth-child(15) .el__body {
  bottom: 20px;
  width: 155px;
  height: 94px;
}
.el__text {
  font-family: 'Montserrat';
  font-style: normal;
  font-weight: 700;
  font-size: 20px;
  line-height: 20px;
  text-align: center;
  text-transform: uppercase;
  color: #ffffff;
  max-width: 210px;
}
.el__head {
  position: absolute;
  /* top: -10px; */
  top: -5%;
  /* left: 17%; */
  left: auto;
  height: 75px;
  width: 185px;
}
.el__body {
  position: absolute;
  /* right: -5%; */
  bottom: 0;
}
</style>
