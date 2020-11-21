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
      progress1: 0,
      progress2: 2000,
      progress3: 3500,
      progress4: 4500
    }
  },

  computed: {
    progressLabel1 () {
      return (this.progress1) + '₽'
    },
    progressLabel2 () {
      return (this.progress1) + '₽'
    }
  }
}
</script>
