<template>
  <div class="q-pa-md">
    <q-linear-progress size="25px" :value="progress1" color="primary">
      <div class="absolute-full flex flex-center">
        <q-badge color="white" text-color="accent" :label="progressLabel1" />
      </div>
    </q-linear-progress>
  </div>
</template>

<script>
export default {
  name: 'progressBar',
  data () {
    return {
      progress1: 0.1,
      progress2: 0.9,
      progress3: 0.2,
      progress4: 0.2
    }
  },

  computed: {
    progressLabel1 () {
      return (this.progress1 * 100).toFixed(2) + 'р'
    }
  }
}
</script>
