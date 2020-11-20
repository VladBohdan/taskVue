<template>
  <div class="q-pa-md">
    <q-layout view="lHh lpr lFf" class="shadow-2 rounded-borders">
      <q-header elevated>
        <q-toolbar class="glossy">
          <q-btn flat round dense icon="menu" class="q-mr-sm" />
          <q-toolbar-title>Личный кабинет</q-toolbar-title>
        </q-toolbar>
      </q-header>
      <personalAccount />
      <q-footer elevated>
        <q-toolbar class="glossy">
          <q-toolbar-title>
            <div class="info">
              <img src="../assets/decision-main.png" height="55" width="60"/>
              <p>© 2018 Супердоставка</p>
              <p>Програмный комплекс для служб доставки</p>
              <p>+7 (960) 555-72-72</p>
              <p>info@superdostavka.net</p>
              <p>Принимаем оплату картами и электронными деньгами</p>
              <img src="../assets/vk.png" height="55" width="90"/>
              <a href="https://vk.com/superdostavka">vk.com/superdostavka</a>
              <img src="../assets/instagram.jpg" height="55" width="115"/>
              <a href="https://www.instagram.com/superdostavka">@superdostavka</a>
              <img src="../assets/decision-main.png" height="55" width="60" alt=""/>
              <p>работает на системе</p>
              <a href="https://superdostavka.net/">супердоставка</a>
            </div>
               </q-toolbar-title>
        </q-toolbar>
      </q-footer>
    </q-layout>

  </div>
</template>
<script>
import personalAccount from '../pages/personalAccount'
export default {
  name: 'MainLayout',
  components: {
    personalAccount
  }
}
</script>
<style>
  .info{

    display: flex;
  }
</style>
