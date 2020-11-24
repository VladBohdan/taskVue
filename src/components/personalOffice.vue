<template>
  <div class="personalOffice">

    <div class="personal-info__wrap">
    <div class="personal-info__block">
      <div class="personal-info__image personal-info__tooltip-wrapper">
        <img class="personal-info__image_contact" src="../assets/contat.png" />
        <q-btn
          class="tooltip-wrapper__button-img"
          fab
          dark
          @click="onEditImgClickedOne()"
        >
          <q-icon dark class="buttonImgEdit">
            +
          </q-icon>
        </q-btn>
        <tooltip class="personal-info__tooltip" :title="title">
          :after
        </tooltip>
      </div>
      <div class="personal-info__contacts">
        <div  class="personal-info__personal-information">
          <strong class="personal-information__name"  >{{name}}</strong>
          <img class="personal information__edit-icon" src="../assets/edit.png" />
          <div class="personal-information__editButton">
            <q-btn
            class="personal-information__buttonEdit"
            fab
            dark
            @click="onEditImgClickedTwo()">
            </q-btn>
          </div>
        </div>
        <div class="personal-information__number">
          <span>{{number}}</span>
        </div>
        <div class="personal-information__personal-password">
          <button
            class="personal-password__edit"
           @click="onEditPasswordSelect()">
           <p>изменить пароль</p>
        </button>
      </div>
      </div>
    </div>
    <div class="personal-info__birthday">
      <div class="personal-birthday__icon">
        <img class="personal-info__icon-birthday" src="../assets/pngegg.png" />
          <div class="personal-birthday__titleOne">
        <div class="personal-birthday__content">
            <strong class="personal-birthday__titleTwo">День рождения</strong>
            <p>Укажите дату рождения, и получите «Калифорнию» в подарок за два дня до и неделю после</p>
          <div class="personal-birthday-select">
            <select-number class="personal-select__number" @clicked="onSelectNumberClicked"></select-number>
            <div>
              <select class="personal-select__months" v-model="selected">
              <option  class="personal-select__title" disabled value="">Выберите месяц</option>
                <option
                class="personal-select__number"
                v-for="post in options"
                     v-bind:key="post.months"
                     v-bind:title="post.months"
                     v-bind:value="post.months"
               >{{post.months}}</option>
              </select>
            </div>
          <div>
            <q-btn class="personal-birthday-button" color="deep-orange" @click="onSaveButtonClick()" glossy
             label="Coхранить" />
          </div>
        </div>
       </div>
        </div>
      </div>
     </div>
    </div>
    <div class="personal-info__bonus">
      <progress-bar :bonuses="bonuses" :current-price="currentPrice"></progress-bar>
    </div>
  </div>
</template>

<script>
import ProgressBar from './progressBar'
import SelectNumber from './selectNumber'
import Tooltip from './tooltip'
export default {
  name: 'personalOffice',
  components: {
    Tooltip,
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
      selected: '',
      selectNumber: 0,
      name: '',
      number: '',
      title: 'По какой-то там причине вам будет полезно загрузить свое фото в профиль',
      currentPrice: 2340,
      bonuses: [
        {
          price: 0,
          percentage: 3
        },
        {
          price: 2000,
          percentage: 5
        },
        {
          price: 3500,
          percentage: 7
        },
        {
          price: 4500,
          percentage: 10
        }
      ]
    }
  },
  methods: {
    onSelectNumberClicked: function (value) {
      this.selectNumber = value
    },
    onSaveButtonClick: function () {
      const requestOptions = {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({ month: this.selected, date: this.selectNumber })
      }
      fetch('https://2acfa8f6fcd2e0c69580a08c0fe9d867.m.pipedream.net', requestOptions)
        .then(response => response.json())
        .then(data => this.onDataSaved(data))
    },
    onDataSaved: function (data) {
    },
    onEditImgClickedOne: function () {
      const requestOptions = {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({ month: this.selected, date: this.selectNumber })
      }
      fetch('https://2acfa8f6fcd2e0c69580a08c0fe9d867.m.pipedream.net', requestOptions)
        .then(response => response.json())
        .then(data => this.onDataSavedImg(data))
    },
    onEditImgClickedTwo: function () {
      const requestOptions = {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({ month: this.selected, date: this.selectNumber })
      }
      fetch('https://2acfa8f6fcd2e0c69580a08c0fe9d867.m.pipedream.net', requestOptions)
        .then(response => response.json())
        .then(data => this.onDataSavedImg(data))
    },
    onEditPasswordSelect: function () {
      const requestOptions = {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({ month: this.selected, date: this.selectNumber })
      }
      fetch('https://2acfa8f6fcd2e0c69580a08c0fe9d867.m.pipedream.net', requestOptions)
        .then(response => response.json())
        .then(data => this.onDataSavedImg(data))
    },
    onDataSavedImg: function (data) {
    },
    onDataLoading: function () {
      const options = {
        method: 'GET',
        headers: { 'Content-Type': 'application/json' }
      }
      fetch('https://2acfa8f6fcd2e0c69580a08c0fe9d867.m.pipedream.net', options)
        .then(resp => resp.json())
        .then(this.onDataLoaded)
    },
    onDataLoaded: function (data) {
      if (data.success) {
        this.name = 'Vlad'
        this.number = '+380 960 931 337'
      }
    }
  },
  mounted () {
    this.onDataLoading()
  }

}

</script>
