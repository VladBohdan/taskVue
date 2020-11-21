<template>
  <div class="q-pa-md q-gutter-sm">
    <q-btn label="Fixed size" color="primary" @click="fixed = true" />
    <q-dialog v-model="fixed">
      <q-card>
        <q-separator />

        <q-card-section style="max-height: 50vh" class="scroll">
          <p>По какoй-то причине вам будет полезно загрузить свое фото в профиль</p>
        </q-card-section>

        <q-separator />

        <q-card-actions align="right">
          <q-btn flat label="X" color="primary" v-close-popup />
        </q-card-actions>
      </q-card>
    </q-dialog>
  </div>
</template>

<script>
export default {
  name: 'modalWindow',
  data () {
    return {
      basic: false,
      fixed: false
    }
  }
}
</script>
