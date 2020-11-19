<template>
  <div class="personalOffice">
    <div class="contactInfo">
      <img src="../assets/contato.png" height="100" width="100"/>
      <div id="name">
        <h1>Name</h1>
        <button>Изменить пароль</button>
      </div>
      <div id="numberPhone">
        <h2>number</h2>
      </div>
      <div id="password">
        <button>изменить пароль</button>
      </div>
    </div>
    <div class="birthday">
      <q-btn
        class="mx-2"
        fab
        dark
        color="indigo"
      >
        <q-icon dark>
          mdi-plus
        </q-icon>
      </q-btn>
      <h1>День рождения</h1>
      <p>Укажите дату рождения, и получите «Калифорнию» в подарок за два дня до и неделю после</p>
      <vSelect></vSelect>
      <q-btn color="deep-orange" glossy label="сохранить" />
      <p> selected option {{selected}}</p>
    </div>
    <div class="bonus">
      <h5>Ваши бонусы</h5>
      <p>текущий уровень кашбэка: 5% (дуйстувует до 20.12.2020)</p>
      <p>Уровень кэшбэка действует с момента получение и до конца следующего месеца. Например,вы получили новий
        уровень 10 апреля-он будет действовать до конца мая. При сумме заказов за месяц от 4500 рублей, вы получаете
        максимальный кашбек - 10%
      </p>
    </div>
  </div>
</template>

<script>
import vSelect from './v-select'
export default {
  name: 'personalOffice',
  components: { vSelect },
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
    selectOption: function (option) {
      this.selected = option.name
    }
  },
  mounted () {
    debugger
    console.log('Add more componente mounted.')
  }
}

</script>
