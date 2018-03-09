<template>
  <div id="app">
    <h1>Translator</h1>
    <form-app v-on:formSub="translate"></form-app>
    <output-text v-bind:translated="translated"></output-text>    
  </div>
</template>

<script>
import TransForm from './components/TransForm.vue';
import Output from './components/Output.vue'

export default {
  
  components: {
    'form-app': TransForm,
    'output-text' : Output
  },
  data: function() {
    return {
      translated : ''
    }
  },
  methods: {
    translate: function(text,language) {
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180308T133525Z.1bf3d4bdb57fe1ad.098f83e904ef9670ae6dcd9d60a28845250bbfab&lang='+language+'&text='+text).then((response)=>{
        this.translated = response.body.text[0];
      });
    }
  }
}
</script>

<style>

</style>
