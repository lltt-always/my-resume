<template>
  <div class="style-editor">
    {{ code }}
  </div>
</template>

<script>
export default {
  name: 'stylesheets-editor',
  props: [ 'code' ],
  data () {
    return {
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
