<template>
  <div class="container">
    <base-language-selector/>
    <div class="logo"></div>
    <img :src="$t('heading')" class="heading" :class="{ animate: loaded }">
    <img :src="$t('heading_m')" class="heading_m" :class="{ animate: loaded }">
    <div class="bonus">
      {{ $t('choose') }}
      <span class="bonus__free">{{ $t('free') }}</span>
      {{ $t('bonus') }}
    </div>
    <div class="gifts">
      <div class="gifts__gift gifts__gift_left gift">
        <div class="gift__heading">{{ $t('offer_item_1_heading') }}</div>
        <div class="gift__subheading">{{ $t('offer_item_1_subheading') }}</div>
        <div class="gift__offer">{{ $t('offer') }}</div>
      </div>
      <div class="gifts__or or">
        <span class="or__text">{{ $t('or') }}</span>
      </div>
      <div class="gifts__gift gifts__gift_right gift">
        <div class="gift__heading">{{ $t('offer_item_2_heading') }}</div>
        <div class="gift__subheading">{{ $t('offer_item_2_subheading') }}</div>
        <div class="gift__offer">{{ $t('offer') }}</div>
      </div>
    </div>
    <div class="slider">
      <div class="slider__heading">
        <div class="slider__text slider__text_video">{{ $t('video') }}</div>
        <div class="slider__text slider__text_screens">{{ $t('screenshots') }}</div>
      </div>
      <the-slider/>
    </div>
    <footer class="footer">
      <img src="../assets/images/gaijin-logo.png" alt="gaijin" class="gaijin">
      <div class="footer__links">               
        <a href="#" class="footer__link">Privacy Policy</a>
        <a href="#" class="footer__link">EULA</a>
        <a href="#" class="footer__link">Terms of Use</a>
        <a href="#" class="footer__link">Customer Support</a>
      </div>
      <img src="../assets/images/pegi.png" alt="age" class="age">
    </footer>
  </div>
</template>
<script>
  import BaseLanguageSelector from './BaseLanguageSelector.vue';
  import TheSlider from './TheSlider.vue';

  export default {
    name: 'TheMainPage',
    data() {
      return {
        loaded: false 
      }
    },
    components: {
      BaseLanguageSelector,
      TheSlider
    },
    created () {
      this.$i18n.locale = 'ru';
      setTimeout(() => {
        this.loaded = true;
      }, 100)
    }
  }
</script>

<style scoped lang="scss">
  @mixin wcolor {
    color: #fff;
  }
  @mixin hovopacity {
    opacity: 0.5;
    transition: 0.3s opacity;
    &:hover {
      opacity: 1;
    }
  }
  .container {
    background: url(~@/assets/images/bg_big.jpg) no-repeat center top;
    position: relative;
    z-index: 1;
    background-size: cover;
    height: 100vh;
    text-align: center;
    box-sizing: border-box;
    min-height: 865px;
    &:after {
      content: " ";
      background: url(~@/assets/images/tank_tower.png) no-repeat center top;
      display: block;
      background-size: cover;
      position: absolute;
      top: 0;
      height: 100vh;
      width: 100%;
      min-height: 865px;
    }
    .logo, .bonus, .gifts {
      position: relative;
      z-index: 2;
    }
  }
  .logo {
    width: 356px;
    height: 201px;
    margin: 0 auto;
    top: 30px;
    margin-bottom: 270px;
    background: url(~@/assets/images/wt-logo-metall.png) no-repeat center;
  }
  .heading {
    position: absolute;
    width: 1280px;
    top: 212px;
    left: 0;
    right: 0;
    margin: 0 auto;
    transition: top 1.5s;
    &.animate {
      top: 192px;
    }
  }
  .heading_m {
    display: none;
  }
  .heading_text {
    display: none;
  }
  .bonus {
    @include wcolor;
    font-size: 36px;
    line-height: 36px;
    text-transform: uppercase;
    font-weight: 500;
    margin-bottom: 30px;
  }
  .bonus__free {
    color: #f8c061;
  }
  .gifts {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 50px;
  }
  .gifts__gift {
    width: 420px;
    height: 128px;
    border-radius: 3px;
    text-align: left;
    background: url(~@/assets/images/bg_block_simple.png) no-repeat center;
    cursor: pointer;
    position: relative;
    border-top: 1px solid #ffa800;
    border-bottom: 1px solid #e25a00;
    border-left: 1px solid #f9893f;
    border-right: 1px solid #f9893f;
  }
  .gifts__gift_left {
    &:after {
      content: "";
      display: block;
      position: absolute;
      width: 241px;
      height: 203px;
      right: -100px;
      top: 0;
      background: url(~@/assets/images/Galers-f3f-2.png) no-repeat center;
    }
    &:hover {
      transform: scale(1.05);
      background: url(~@/assets/images/bg_block_airplane.png) no-repeat center;
    }
  }
  .gifts__gift_right {
    &:after {
      content: "";
      display: block;
      position: absolute;
      width: 248px;
      height: 202px;
      right: -50px;
      top: -42px;
      background: url(~@/assets/images/light-tank-m2a4.png) no-repeat center;
    }
    &:hover {
      transform: scale(1.05);
      background: url(~@/assets/images/bg_block_tank.png) no-repeat center;
    }
  }
  .gift__heading {
    font-size: 24px;
    @include wcolor;
    text-transform: uppercase;
    font-weight: 700;
    margin-top: 20px;
    margin-bottom: 3px;
    margin-left: 26px;
    line-height: 1;
  }
  .gift__subheading {
    font-size: 30px;
    @include wcolor;
    text-transform: uppercase;
    font-weight: 700;
    margin-left: 26px;
    margin-bottom: 15px;
    line-height: 1;
  }
  .gift__offer {
    color: #f9c064;
    font-size: 20px;
    text-transform: uppercase;
    font-weight: 500;
    margin-left: 26px;
  }
  .or {
    background: url(~@/assets/images/icon_or.png) no-repeat center;
    width: 113px;
    height: 104px;
    line-height: 104px;
    color: #000;
    margin: 0 30px;
    font-size: 21.5px;
    font-weight: 700;
    text-transform: uppercase;
  }
  .slider {
    z-index: 3;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 50px;
  }
  .slider__heading {
    font-size: 24px;
    @include wcolor;
    font-weight: 500;
    text-transform: uppercase;
    text-align: right;
    margin-right: 15px;
  }
  .gaijin, .age {
    @include hovopacity;
    cursor: pointer;
  }
  .gaijin {
    margin-left: 31px;
  }
  .age {
    margin-right: 28px;
  }
  .footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: absolute;
    bottom: 35px;
    z-index: 2;
    width: 100%;
  }
  .footer__link {
    color: #b4b5b8;
    font-size: 14.5px;
    margin-right: 20px;
    &:last-child {
      margin-right: 0;
    }
  }
  @media(max-width: 1919px) {
    .container {
      min-width: 1024px;
      min-height: 618px;
      &:after {
        min-height: 618px;
      }
    }
    .logo {
      width: 210px;
      background-size: contain;
      top: 0;
      margin-bottom: 115px;
    }
    .heading {
      width: 800px;
      top: 165px;
      &.animate {
        top: 150px;
      }
    }
    .bonus {
      font-size: 24px;
      margin-bottom: 20px;
    }
    .gift {
      width: 360px;
      height: 110px;
    }
    .gift__heading {
      font-size: 18px;
    }
    .gift__subheading {
      font-size: 24px;
    }
    .gift__offer {
      font-size: 16px;
    }
    .gifts__gift_left:after {
      width: 166px;
      height: 139.81px;
      right: -60px;
      background-size: contain;
    }
    .gifts__gift_right:after {
      background-size: contain;
    }
    .gifts {
      margin-bottom: 20px;
    }
    .or {
      width: 87px;
      height: 80px;
      background-size: contain;
      line-height: 80px;
      font-size: 18px;
    }
    .footer {
      bottom: 15px;
    }
  }
  @media(max-width: 1023px) {
    .container {
        min-width: 320px;
        min-height: 100vh;
        padding-bottom: 36px;
        height: inherit;
        &:after {
          display: none;
        }
    }
    .logo {
      width: 160px;
      height: 90.33px;
      margin-bottom: 20px;
      top: 23px;
    }
    .heading_m {
      display: block;
      margin: 0 auto 130px auto;
    }
    .heading {
      display: none;
    }
    .bonus {
      font-size: 36px;
      max-width: 400px;
      margin: 0 auto 36px auto;
      padding: 0 10px;
    }
    .gifts {
      margin-bottom: 58px;
    }
    .gift {
      width: 140px;
      height: 220px;
      z-index: 2;
      background: rgba(43, 17, 16, 0.71);
      &:before {
        content: " ";
        display: block;
        position: absolute;
        width: 140px;
        height: 140px;
        top: 55px;
        background: radial-gradient(rgba(226, 188, 0, 0.7) 0%, rgba(226, 90, 0, 0.85) 30%, transparent 70%, transparent 100%);
      }
      &:hover {
        background: rgba(43, 17, 16, 0.71);
      }
    }
    .or {
      position: absolute;
      z-index: 1;
      margin: 0 auto;
    }
    .gift__heading {
      position: relative;
      margin-left: 17px;
      margin-top: 17px;
    }
    .gift__subheading, .gift__offer {
      position: relative;
      margin-left: 17px;
    }
    .gift__subheading {
      margin-bottom: 80px;
    }
    .gift__offer {
      font-size: 13px;
      line-height: 1.38;
      position: absolute;
      bottom: 20px;
    }
    .gifts__gift_left {
      margin-right: 5px;
      &:after {
        width: 117px;
        height: 98.55px;
        right: 0;
        top: 85px;
      }
    }
    .gifts__gift_right {
      &:after {
        width: 117px;
        height: 95.3px;
        right: 12px;
        top: 85px;
      }
    }
    .slider {
      display: block;
    }
    .slider__heading {
      display: flex;
      justify-content: center;
      text-align: left;
      margin-right: 0;
      margin-bottom: 20px;
    }
    .footer {
      position: relative;
      display: block;
      width: 280px;
      margin: 0 auto;
      bottom: inherit;
      min-height: 110px;
    }
    .footer__links {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
    }
    .footer__link {
      margin-bottom: 10px;
    }
    .gaijin, .age {
      position: absolute;
      margin: 0;
      bottom: 0;
    }
    .gaijin {
      left: 0;
    }
    .age {
      right: 0;
    }
  }
  @media(max-width: 700px) {
    .container {
      background: url(~@/assets/images/bg_m.jpg) no-repeat center top, #0f090a;
    }
  }
</style>
