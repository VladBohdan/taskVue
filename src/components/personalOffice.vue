<template>
  <div class="personalOffice">
    <div class="contactInfo">
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
      <div id="name">
        <p>Name</p>
        <button>Изменить пароль</button>
      </div>
      <div id="numberPhone">
        <p>number</p>
      </div>
      <div id="password">
        <button>изменить пароль</button>
      </div>
    </div>
    <div class="birthday">
      <img src="../assets/present.jpg" height="125" width="140"/>
      <span>День рождения</span>
      <p>Укажите дату рождения, и получите «Калифорнию» в подарок за два дня до и неделю после</p>
      <div
        v-for="post in options"
        v-bind:key="post.months"
        v-bind:title="post.months"
      >
      </div>
      <select v-model="selected">
        <option disabled value="">Выберите один из вариантов</option>
        <option v-for="post in options"
                v-bind:key="post.months"
                v-bind:title="post.months"
                v-bind:value="post.months"
        >{{post.months}}</option>
      </select>
      <span>Выбрано: {{ selected }}</span>
      <vSelect></vSelect>
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
import vSelect from './v-select'
import ProgressBar from './progressBar'
export default {
  name: 'personalOffice',
  components: {
    ProgressBar,
    vSelect
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
.personalOffice{
  display: flex;
  align-items: center;
  flex-direction: column;
  width: 100%;
  text-align: center;
  margin: 10% 0;
  min-height: 200px;
  background-color: rgba(33, 33, 33, .3);
}

.contactInfo {
  display: flex;
  align-items: center;
  flex-direction: column;
  width: 30%;
  text-align: center;
  margin: 10% 0;
  min-height: 200px;
  background-color: blueviolet;
  Justify-content: flex-start;
}
.birthday {
  display: flex;
  align-items: center;
  flex-direction: column;
  width: 50%;
  text-align: center;
  margin: 10% 0;
  min-height: 200px;
  background-color: orange;
  justify-content: flex-end;
}
  .bonus{
    margin: 10% 0;
    min-height: 200px;
    background-color: dodgerblue;
  }
</style>
