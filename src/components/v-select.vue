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
