<template>
  <div class="progressBar">
    <strong class="progressBar-titleOne">Ваши бонусы</strong>
    <b class="progressBar-bonus">x{{value}}</b>
    <progress class="progressBar-progress" :value="value" :max="max" show-progress animated></progress>
    <p class="progressBar-titleTwo">Сума заказов в Июне 2340 ₽</p>
  </div>

</template>

<script>
export default {
  name: 'progressBar',
  data () {
    const val = 1226
    // this.value = (val * 100) / 4500
    return {
      min: 0,
      value: val,
      max: 4500
    }
  },
  methods: {
    randomValue (value) {
      // let oneProcentStep = 1000
      // const a = ((value * 100) / 4500) / 10
      if (value > 2000 && value < 3500) {
        // oneProcentStep = 750
        this.min = 5
        this.max = 10
      } else if (value > 3500 && value < 4500) {
        // oneProcentStep = 500
        this.min = 7
        this.max = 10
        this.value = ((value * 100) / 4500) / 10
      }
    }
  }
}
</script>
<style>
  progress{
    width: 100%

  }
</style>
