<template>
  <div id="app">
    <stylesheets-editor ref="stylesheetseditor" :code="currentStyle"></stylesheets-editor>
    <resume-editor ref="resumeeditor"></resume-editor>
  </div>
</template>

<script>
import StylesheetsEditor from './components/StylesheetsEditor'
import ResumeEditor from './components/ResumeEditor'

export default {
  name: 'app',
  components: {
    StylesheetsEditor, ResumeEditor
  },
  data: function() {
    return {
      fullStyles: [
        `* {
          padding: 0;
          margin: 0;
        }
        body {
          background-color: #f00;
        }`
      ],
      currentStyle: '',
      interval: 5,
    }
  },
  mounted: function() {
    this.showStyle(0);
  },
  methods: {
    showStyle: function(index){
      let _this = this;
      let outputStyle = function() {
        let l = _this.currentStyle ? _this.currentStyle.length : 0;
        let char = _this.fullStyles[index].substring(l, l+1);
        if(char == '\n'){}
        _this.currentStyle +=char;
        if(char){
          setTimeout(outputStyle, _this.interval)
        }
      };
      outputStyle()
    }
  }
}
</script>

<style>
#app {
}
</style>
