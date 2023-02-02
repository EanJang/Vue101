<template>
    <button>Turn me {{ color }}</button>
</template>

<script>
export default {
  name: 'ColorButton',
  props: {
    color: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
