<template>
  <div class="personalAccount">
<!--
    <router-view></router-view>
-->
    <personalOffice></personalOffice>
  </div>
</template>

<script>
import personalOffice from '../components/personalOffice'
export default {
  name: 'personalAccount',
  components: {
    personalOffice
  }
}
</script>
