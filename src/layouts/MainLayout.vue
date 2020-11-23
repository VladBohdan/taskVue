<template>
  <div class="q-pa-md MainLayout">
    <q-layout view="lHh lpr lFf" class="shadow-2 rounded-borders MainLayout-info__layout">
      <q-header elevated class="MainLayout-header">
        <q-toolbar class="glossy MainLayout-header__toolbar">
          <q-btn flat round dense icon="menu" class="q-mr-sm MainLayout-header__button" />
          <q-toolbar-title class="MainLayout-header__title">Личный кабинет</q-toolbar-title>
        </q-toolbar>
      </q-header>
      <personalAccount />
      <q-footer elevated class="MainLayout-footer">
        <q-toolbar class="glossy MainLayout-footer__toolbar">
          <q-toolbar-title class="glossy MainLayout-footer__titleToolbar">
            <div class="info glossy MainLayout-footer__info">
              <img class="MainLayout-info__iconOne" src="../assets/decision-main.png" height="55" width="60"/>
              <p class="MainLayout-info__titleOne">© 2018 Супердоставка</p>
              <p class="MainLayout-info__titleTwo">Програмный комплекс для служб доставки</p>
              <p class="MainLayout-info__titleThree">+7 (960) 555-72-72</p>
              <p class="MainLayout-info__titleFour">info@superdostavka.net</p>
              <p class="MainLayout-info__titleFive">Принимаем оплату картами и электронными деньгами</p>
              <img class="MainLayout-info__iconTwo" src="../assets/vk.png" height="55" width="90"/>
              <a class="MainLayout-info__linkOne" href="https://vk.com/superdostavka" >vk.com/superdostavka</a>
              <img class="MainLayout-info__iconThree" src="../assets/instagram.jpg" height="55" width="115"/>
              <a class="MainLayout-info__linkTwo" href="https://www.instagram.com/superdostavka">@superdostavka</a>
              <img class="MainLayout-info__iconFour" src="../assets/decision-main.png" height="55" width="60" alt=""/>
              <p class="MainLayout-info__titleSix">работает на системе</p>
              <a class="MainLayout-info__linkThree" href="https://superdostavka.net/">супердоставка</a>
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
