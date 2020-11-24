<template>
  <div class="q-pa-md MainLayout">
    <q-layout view="lHh lpr lFf" class="shadow-2 rounded-borders MainLayout-info__layout">
      <q-header elevated class="MainLayout-header">
        <q-toolbar class="glossy MainLayout-header__toolbar">
          <q-btn flat round dense icon="menu" class="q-mr-sm MainLayout-header__button" />
          <q-toolbar-title class="MainLayout-header__title">Личный кабинет</q-toolbar-title>
        </q-toolbar>
      </q-header>
      <router-view></router-view>
      <q-footer elevated class="MainLayout-footer">
        <q-toolbar class="glossy MainLayout-footer__toolbar">
          <q-toolbar-title class="glossy MainLayout-footer__titleToolbar">
            <div class="info glossy MainLayout-footer__info">
              <div class="MainLayout-footer__contact-info">
                <div class="contact-info">
                  <img class="contact-info__icon-logo" src="../assets/decision-main.png"/>
                  <div class="constant-info__title">
                    <bold class="title__title-name">© 2018 Супердоставка</bold>
                    <p class="title__title-info">Програмный комплекс для служб доставки</p>
                  </div>
                </div>
                <div class="MainLayout-footer__contact-information">
                  <p class="contact-information__title-number">+7 (960) 555-72-72</p>
                  <p class="contact-information__title-mail">info@superdostavka.net</p>
                </div>
              </div>
              <div class="MainLayout-footer__info-social">
                <div class="info-social__cashless-payment">
                  <img class="cashless-payment__icon" src="../assets/bank-cards--v1.png" />
                  <p class="cashless-payment__title" style="color: #1D1D1D !important;">Принимаем оплату картами и электронными
                    деньгами</p>
                </div>
                <div class="MainLayout-footer__info-social-link">
                  <img class="info-social-link__iconVk" src="../assets/vk.png"/>
                  <a class="info-social-link__linkVk" href="https://vk.com/superdostavka" >vk.com/superdostavka</a>
                  <img class="info-social-link__iconInstagram" src="../assets/instagram.png"/>
                  <a class="info-social-link__Instagram" href="https://www.instagram.com/superdostavka">@superdostavka</a>
                </div>
              </div>
              <div class="MainLayout-footer__info-superdostavka">
                <div class="info-superdostavka__work-info">
                  <img class="work-info__iconFour" src="../assets/decision-main.png"  alt=""/>
                  <div class="work-info__title">
                    <p class="title__work">работает на системе</p>
                    <a class="title__link" href="https://superdostavka.net/">супердоставка</a>
                  </div>
                </div>
              </div>
            </div>
               </q-toolbar-title>
        </q-toolbar>
      </q-footer>
    </q-layout>

  </div>
</template>
<script>
export default {
  name: 'MainLayout',
  components: {
  }
}
</script>
<style>
  .info{

    display: flex;
  }
</style>
