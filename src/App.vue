<template>
  <div id="app">
    <the-main-page/>
  </div>
</template>

<script>
  import TheMainPage from './components/TheMainPage.vue';
  import 'reset-css';

  export default {
    name: 'app',
    components: {
      TheMainPage
    }
  }
</script>

<style lang="scss">
  @font-face {
      font-family: 'FiraSans';
      src: url('./assets/fonts/Firasansregular.woff2') format('woff2'),
           url('./assets/fonts/Firasansregular.woff') format('woff');
      font-weight: normal;
      font-style: normal;
  }
  @font-face {
      font-family: 'FiraSans';
      src: url('./assets/fonts/Firasansbold.woff2') format('woff2'),
           url('./assets/fonts/Firasansbold.woff') format('woff');
      font-weight: 700;
      font-style: normal;
  }
  @font-face {
      font-family: 'FiraSans';
      src: url('./assets/fonts/Firasansmedium.woff2') format('woff2'),
           url('./assets/fonts/Firasansmedium.woff') format('woff');
      font-weight: 500;
      font-style: normal;
  }
  @mixin slider_btn {
    font-size: 0;
    width: 50px;
    height: 50px;
    border: 1px solid #fff;
    border-radius: 0;
  }
  * {
    outline: none;
  }
  .container {
    font-family: 'FiraSans', sans-serif;
    .slider {
      .prev {
        background: url(~@/assets/images/icon-prev.png) no-repeat center;
        @include slider_btn;
      }
      .next {
        background: url(~@/assets/images/icon-next.png) no-repeat center;
        @include slider_btn;
      }
      .close {
        padding: 0;
        background: url(~@/assets/images/icon-close.png) no-repeat center;
        @include slider_btn;
        border-top-color: transparent;
        border-right-color: transparent;
      }
    }
  }
</style>