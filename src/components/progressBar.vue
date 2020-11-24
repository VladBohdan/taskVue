<template>
  <div class="progress-bar__wrapper">
    <div class="progressBar">
      <strong class="progressBar-title-bonus">Ваши бонусы</strong>
      <div class="progress-bar__score">
        <img class="score_img-bonus" src="../assets/bonus.png" />
        <b class="score-price">x{{price}}</b>
      </div>
    </div>
    <div class="progress-bar__line-wrapper">
      <div class="progress-bar__line-gray"></div>
      <div class="progress-bar__line-yellow" v-bind:style="{width:percentage+'%'}">{{percentage}}</div>
      <div class="progress-bar__line-block"
        v-for="point in points"
        v-bind:key="point.price"
        :style="{left: point.width + '%'}">
        <div class="progress-bar__info">
          {{point.price+'₽'}}
          {{point.percentage+'%'}}
        </div>
        <span class="progress-bar__line-point" :class="{active: point.completed}" ></span>
      </div>
    </div>
    <div class="progress-bar__bonus-info">
      <img class="bonus-info__title_img" src="../assets/vector.png" />
      <b class="bonus-info__price" >Сума заказов в Июне {{price}} ₽</b>
      </div>
    <div class="progress-bar__personal-bonus">
      <strong class="personal-bonus__lvl-cashback">
        Текущий уровень кашбэка: {{percentage+'%'}} (дейстувует до 20.12.2020)
      </strong>
      <p
        class="personal-bonus__rules">
        Уровень кэшбэка действует с момента получение и до конца следующего месеца.
        Например,вы получили новий
        уровень 10 апреля-он будет действовать до конца мая. При сумме заказов за месяц от 4500 рублей, вы получаете
        максимальный кашбек - 10%
      </p>
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
        completed: b.price < currentPrice
      }))
    }
  }
}
</script>
<style>
</style>
