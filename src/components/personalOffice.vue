<template>
  <div class="personalOffice">
    <div class="personal-info__wrap">
    <div class="personal-info__block">
      <div class="personal-info__image">
      <img src="../assets/contat.png" height="100" width="100"/>
      <q-btn
        class="buttonPlus"
        fab
        dark
        color="indigo"
      >
        <q-icon dark>
          +
        </q-icon>
      </q-btn>
     </div>
      <div class="personal-info__contacts">
      <div id="name">
        <span>Name</span>
      </div>
      <div id="numberPhone">
        <span>number</span>
      </div>
      <div id="password">
        <button>изменить пароль</button>
      </div>
      </div>
    </div>
    <div class="personal-info__birthday">
      <div class="personal-birthday__icon">
      <img src="../assets/pngegg.png" height="125" width="140"/>
        <div class="personal-birthday__title">
      <div class="personal-birthday__content">
        <span>test</span>
        <p>Укажите дату рождения, и получите «Калифорнию» в подарок за два дня до и неделю после</p>

        <div class="personal-birthday-select">
          <select-number></select-number>
          <div>
          <select v-model="selected">
            <option disabled value="">Выберите один из вариантов</option>
            <option v-for="post in options"
                    v-bind:key="post.months"
                    v-bind:title="post.months"
                    v-bind:value="post.months"
            >{{post.months}}</option>
          </select>
          </div>
          <div>
          <q-btn color="deep-orange" glossy label="Coхранить" />
          </div>
        </div>
      </div>
        </div>
      </div>
     </div>
    </div>
    <div class="bonus">
      <progress-bar></progress-bar>
      <p>Ваши бонусы</p>
      <p>текущий уровень кашбэка: 5% (дуйстувует до 20.12.2020)</p>
      <p>Уровень кэшбэка действует с момента получение и до конца следующего месеца. Например,вы получили новий
        уровень 10 апреля-он будет действовать до конца мая. При сумме заказов за месяц от 4500 рублей, вы получаете
        максимальный кашбек - 10%
      </p>
    </div>

  </div>
</template>

<script>
import ProgressBar from './progressBar'
import SelectNumber from './selectNumber'
export default {
  name: 'personalOffice',
  components: {
    SelectNumber,
    ProgressBar
  },
  data: function () {
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
      selected: 'roma'
    }
  },
  methods: {
    selectOption: function (option) {
      this.selected = option.name
    }
  },
  mounted () {
    console.log('Add more componente mounted.')
  }
}

</script>

<style>

.contactInfo {
  background-color: blueviolet;
  Justify-content: flex-start;
}
.birthday {
  display: flex;
  align-items: center;
  flex-direction: column;
  width: 50%;
  text-align: center;
  background-color: orange;
}
  .bonus{
    min-height: 200px;
    background-color: dodgerblue;
    justify-content: flex-end;
  }
</style>
