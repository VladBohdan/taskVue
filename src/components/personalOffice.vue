<template>
  <div class="personalOffice">
    <div class="contactInfo">
      <img src="#" alt="#">
      <div id="name">
        <h1>Name</h1>
      </div>
      <div id="numberPhone">
        <h2>number</h2>
      </div>
      <div id="password">
        <button>изменить пароль</button>
      </div>
    </div>
    <div class="birthday">
      <img src="#" alt="#">
      <h1>День рождения</h1>
      <p>Укажите дату рождения, и получите «Калифорнию» в подарок за два дня до и неделю после</p>
      <!-- <select v-model="numberMonths" id="numberMonths">{{number}}</select>
       <select v-model="months"  id="months">{{months}}</select>-->
      <v-select
      :options="options"
      @select="optionSelect"
      :selected="selected"
      />
      <p> selected option {{selected}}</p>
    </div>
    <div class="bonus"></div>
  </div>
</template>

<script>
import vSelect from './v-select'
export default {
  name: 'personalOffice',
  comments: {
    vSelect
  },
  data () {
    return {
      options: [
        {
          months: 'Январь ',
          value: 1
        },
        {
          months: 'Февраль ',
          value: 2
        },
        {
          months: 'Март  ',
          value: 3
        },
        {
          months: 'Апрель  ',
          value: 4
        },
        {
          months: 'Май  ',
          value: 5
        },
        {
          months: 'Июнь  ',
          value: 6
        },
        {
          months: 'Июль  ',
          value: 7
        },
        {
          months: 'Август  ',
          value: 8
        },
        {
          months: 'Сентябрь  ',
          value: 9
        },
        {
          months: 'Октябрь  ',
          value: 10
        },
        {
          months: 'Ноябрь  ',
          value: 11
        },
        {
          months: 'Декабрь  ',
          value: 12
        }
      ],
      selected: 'Select'
    }
  },
  methods: {
    selectOption(option) {
      this.selected = option.name
    }
  }
}
</script>
