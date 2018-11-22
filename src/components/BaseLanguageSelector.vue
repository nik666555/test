<template>
  <div class="localization">
    <multiselect v-model="value" :options="options" :searchable="false" :close-on-select="true" :show-labels="false" :allow-empty="false" placeholder="Choose language">
      <template slot="singleLabel" slot-scope="props"><img class="option__image" :src="props.option.img" alt="No Man’s Sky"><span class="option__desc"><span class="option__title">{{ props.option.title }}</span></span></template>
      <template slot="option" slot-scope="props"><img class="option__image" :src="props.option.img" alt="No Man’s Sky"></template>
    </multiselect>
  </div>
</template>

<script>
  import Multiselect from 'vue-multiselect';
  import ru from '@/assets/flags/Russia.png';
  import tr from '@/assets/flags/Turkey.png'

  export default {
    name: 'BaseLanguageSelector',
    components: { Multiselect },
    data () { 
      return { 
        locale: 'ru',
        value: { title: 'ru', img: ru },
        options: [
          { title: 'ru', img: ru },
          { title: 'tr', img: tr}
        ]
      } 
    },
    watch: {
      value (val) {
        this.$i18n.locale = val.title
      }
    }
  }
</script>
<style scoped>
  .localization {
    position: absolute;
    right: 0;
    z-index: 2;
    width: 32px;
    height: 32px;
    right: 20px;
    top: 20px;
    cursor: pointer;
  }
  .vl {
    color: #fff;
    font-size: 30px;
  }
</style>
<style>

  .option__desc {
    color: #fff;
  }
</style>