<template>
  <div class="q-pa-md">
    <q-layout view="lHh lpr lFf" class="shadow-2 rounded-borders">
      <q-header elevated>
        <q-toolbar class="glossy">
          <q-btn flat round dense icon="menu" class="q-mr-sm" />
          <q-toolbar-title>Личный кабинет</q-toolbar-title>
        </q-toolbar>
      </q-header>

      <q-footer elevated>
        <q-toolbar class="glossy">
          <q-toolbar-title>Footer</q-toolbar-title>
        </q-toolbar>
      </q-footer>
    </q-layout>
  </div>
</template>
<script>
export default {
  name: 'MainLayout'
}
</script>
