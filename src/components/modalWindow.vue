<template>
  <form class="modalWindow">
    <div id="anim" class="modalWindow-info__block">
      <span  class="modalWindow-block__title"
             data-tooltip="По какой-то причине вам будет полезно загрузить свое фото в профиль"
      >
      </span>
    </div>
  </form>
</template>

<script>
export default {
  name: 'progressBar'
}
</script>
<style>
  .modalWindow-block__title {
    position: relative;
    padding: 23px 30px;
    margin: 5px;
    font-size: 15px;
    border-radius: 100%;
    color: #1D1D1D;
    top: -55px;
    left: 2px;

  }

  .modalWindow-block__title:before,
  .modalWindow-block__title:after {
    background: #ffffff;
    position: absolute;
    content: '';
    opacity: 0;
    transition: all 0.4s ease;
  }

  .modalWindow-block__title:before {
    border-width: 10px 8px 0 8px;
    border-style: solid;
    top: -15px;
    transform: translateY(20px);
  }

  .modalWindow-block__title:after {
    content: attr(data-tooltip);
    width: 160px;
    height: 40px;
    font-size: 13px;
    font-weight: 300;
    top: -75px;
    left: -10px;
    padding: 10px;
    border-radius: 5px;
    letter-spacing: 1px;
    transform: translateY(40px);
  }

  .modalWindow-block__title:hover::before,
  .modalWindow-block__title:hover::after {
    opacity: 1;
    transform: translateY(-2px);
  }
</style>
