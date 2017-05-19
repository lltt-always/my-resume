<template>
  <div class="style-editor">
    <div v-html="stylecode"></div>
    <pre class="language-css">{{ code }}</pre>
  </div>
</template>

<script>
export default {
  name: 'stylesheets-editor',
  props: [ 'code' ],
  data () {
    return {
    }
  },
  computed: {
    stylecode: function() {
      return `<style> ${this.code} </style>`
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
