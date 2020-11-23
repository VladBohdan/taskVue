<template>
  <div class="progress-bar__wrapper">
    <div class="progressBar">
      <strong class="progressBar-titleOne">Ваши бонусы</strong>
      <b class="progressBar-bonus">x{{price}}</b>
      <p class="progressBar-titleTwo">Сума заказов в Июне 2340 ₽</p>
    </div>
    <div class="progress-bar__line-wrapper">
      <div class="progress-bar__line-gray"></div>
      <div class="progress-bar__line-yellow" v-bind:style="{width:percentage+'%'}">{{percentage}}</div>
     <!-- <div class="point"
        v-for="point in points"
         :key="point"
        v-bind:style="{left:point.width}"
        v-bind:class="{active: point.completed}"></div>-->
    </div>
  </div>
</template>

<script>
export default {
  name: 'progressBar',
  props: {
    currentPrice: Number,
    bonuses: Array // {price:number,percentage:number}
  },
  data () {
    console.log(this.getMaxBonus(this.bonuses))
    return {
      price: this.currentPrice,
      points: this.mapPoints(this.bonuses, this.currentPrice),
      percentage: this.currentPrice / this.getMaxBonus(this.bonuses) * 100
    }
  },
  methods: {
    getMaxBonus (bonuses) {
      return Math.max(...bonuses.map(b => b.price))
    },
    mapPoints (bonuses, currentPrice) {
      return bonuses.map(b => ({
        ...b,
        width: b.price / this.getMaxBonus(bonuses) * 100,
        completed: b.price > currentPrice
      }))
    }
  }
}
</script>
<style>
</style>
