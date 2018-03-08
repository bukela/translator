<template>
  <div id="app">
    <h1>Translator</h1>
    <form-app v-on:formSub="translate"></form-app>
    <output-text></output-text>    
  </div>
</template>

<script>
import TransForm from './components/TransForm'
import Output from './components/Output'

export default {
  name: 'App',
  components: {
    'form-app': TransForm,
    'output-text' : Output
  },
  data() {
    return {
      
    }
  },
  methods: {
    translate: function(text) {
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180308T133525Z.1bf3d4bdb57fe1ad.098f83e904ef9670ae6dcd9d60a28845250bbfab&lang=ru&text='+text).then((response)=>{
        console.log(response.body.text[0]);
      });
    }
  }
}
</script>

<style>

</style>
