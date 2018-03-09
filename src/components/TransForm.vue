<template>
  <div id="transForm">
      <form v-on:submit="formSub">
          <input type="text" v-model="textForTrans" name="" id="">
          
          <select v-model="language" v-bind:class="{ language:'' }">
              <option value="ru">Russian</option>
              <option value="es">Spanish</option>
              <option value="fr">French</option>
              <option value="it">Italian</option>
              <option value="de">German</option>
          </select>
          <input type="submit" value="Translate">
      </form>
  </div>
</template>

<script>


export default {
    
    data() {
        return {
            textForTrans: '',
            language: ''
            
        }
    },
    created() {
        this.language = 'ru';
    },
    methods: {
        formSub: function(e) {
            e.preventDefault();
            this.$emit('formSub', this.textForTrans,this.language);
        } 
    }
}
</script>

<style>

</style>
