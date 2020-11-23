<template>
  <div  class="tooltip">
    {{ text }}
  </div>
</template>
<script>
export default {
  name: 'tooltip',
  props: ['title'],
  data: function () {
    return {
      text: this.title
    }
  }
}
</script>
