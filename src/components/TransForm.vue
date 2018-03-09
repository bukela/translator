<template>
  <div id="transForm">
      <form v-on:submit="formSub">
          <input type="text" v-model="textForTrans" name=""  placeholder="From English to :">
          
          <select v-model="language">
              <option value="ru">Russian</option>
              <option value="es">Spanish</option>
              <option value="fr">French</option>
              <option value="it">Italian</option>
              <option value="de">German</option>
              <option value="sr">Serbian</option>
          </select>
        <input type="submit" value="Translate">
        <div v-bind:class="language"></div>
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
.ru {
    background : url('../img/russia.png') no-repeat center center/cover;
    width: 50px;
    height: 50px;
    margin: 10px; 
}
.es {
    background : url('../img/spain.png') no-repeat center center/cover;
    width: 50px;
    height: 50px;
    margin: 10px;  
}
.fr {
    background : url('../img/france.png') no-repeat center center/cover;
    width: 50px;
    height: 50px;
    margin: 10px;  
}
.it {
    background : url('../img/italy.png') no-repeat center center/cover;
    width: 50px;
    height: 50px;
    margin: 10px; 
}
.de {
    background : url('../img/germany.png') no-repeat center center/cover;
    width: 50px;
    height: 50px;
    margin: 10px;  
}
.sr {
    background : url('../img/serbia.png') no-repeat center center/cover;
    width: 50px;
    height: 50px;
    margin: 10px;  
}
</style>
