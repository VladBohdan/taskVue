<template>
  <div id="q-app">
    <div class="q-pa-md" style="max-width: 300px">
      <div class="q-gutter-md">
        <q-select v-model="model" :options="options" label="" value="2"></q-select>
      </div>
      <label>
        <div
          v-for="post in options"
          v-bind:key="post.number"
          v-bind:number="post.number"
        >
        </div>
        <select v-model="selected">
          <option disabled value="">Выберите один из вариантов</option>
          <option v-for="post in options"
                  v-bind:key="post.number"
                  v-bind:title="post.number"
                  v-bind:value="post.number"
          ></option>
        </select>
      </label>
      <div
        class="options"
      >
        <p
          v-for="option in options"
          :key="option.value"
          @click="selectOptionNumber(option)"
        >
        </p>
      </div>
    </div>
    <span>Выбрано: {{ selected }}</span>
    </div>
</template>
<script>
export default {
  name: 'selectNumber',
  data () {
    return {
      model: null,
      options: [
        {
          name: '1',
          value: 1
        },
        {
          name: '2',
          value: 2
        },
        {
          name: '3',
          value: 3
        },
        {
          name: '4',
          value: 4
        },
        {
          name: '5',
          value: 5
        },
        {
          name: '6',
          value: 6
        },
        {
          name: '7',
          value: 7
        },
        {
          name: '8',
          value: 8
        },
        {
          name: '9',
          value: 9
        },
        {
          name: '10',
          value: 10
        },
        {
          name: '11',
          value: 11
        },
        {
          name: '12',
          value: 12
        },
        {
          name: '13',
          value: 13
        },
        {
          name: '14',
          value: 14
        },
        {
          name: '15',
          value: 15
        },
        {
          name: '16',
          value: 16
        },
        {
          name: '17',
          value: 17
        },
        {
          name: '18',
          value: 18
        },
        {
          name: '19',
          value: 19
        },
        {
          name: '20',
          value: 20
        },
        {
          name: '21',
          value: 21
        },
        {
          name: '22',
          value: 22
        },
        {
          name: '23',
          value: 23
        },
        {
          name: '24',
          value: 24
        },
        {
          name: '25',
          value: 25
        },
        {
          name: '26',
          value: 26
        },
        {
          name: '27',
          value: 27
        },
        {
          name: '28',
          value: 28
        },
        {
          name: '29',
          value: 29
        },
        {
          name: '30',
          value: 30
        },
        {
          name: '31',
          value: 31
        }
      ],
      selected: '1'
    }
  },
  methods: {
    selectOption: function (option) {
      this.selected = option.name
    }
  }
}
</script>
