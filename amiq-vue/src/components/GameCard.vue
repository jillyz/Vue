<template>
  <div class="amiq-card" :data-card="`${num}`">
    {{num}}
  </div>
</template>

<script>
export default {
  name: 'GameCard',
  props: {
    num: Number
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
