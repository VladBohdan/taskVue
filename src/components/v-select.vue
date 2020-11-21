<template>
  <div class="v-select">
    <p
      @click="areOptionsVisible = !areOptionsVisible"
      class="title"
    ></p>
    <div
      class="options"
      v-if="areOptionsVisible"
    >
      <p
        v-for="option in options"
        :key="option.value"
        @click="selectOption(option)"
      >
        {{option.name}}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'v-select',
  props: {
    options: {
      type: Array,
      default () {
        return []
      }
    },
    selected: {
      type: String,
      default: ''
    }
  },
  data () {
    return {
      areOptionsVisible: false
    }
  },
  methods: {
    selectOption: function (option) {
      this.$emit('select', option)
      this.areOptionsVisible = false
    },
    hidenSelect: function () {
      this.areOptionsVisible = false
    }
  },
  mounted () {
    document.addEventListener('click', this.hidenSelect.bind(this), true)
  },

  beforeDestroy () {
    document.removeEventListener('click', this.hidenSelect)
  }
}
</script>

<style>
  .v-select {
    position: relative;
    width: 200px;
    cursor: pointer;
  }

  .v-select p {
    margin: 0;
  }

  .title {
      border: solid 1px #1D1D1D;
  }

  .options {
    border: solid 1px #1D1D1D;
    position: absolute;
    top: 25px;
    right: 0;
    width: 100%;
  }

  .options p:hover{
    background: #1D1D1D;
  }
</style>
