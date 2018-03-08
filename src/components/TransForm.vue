<template>
  <div id="transForm">
      <form v-on:submit="formSub">
          <input type="text" v-model="textForTrans" name="" id="">
          <input type="submit" value="Translate">
      </form>
  </div>
</template>

<script>


export default {
    name: 'transForm',
    data() {
        return {
            textForTrans: ''
        }
    },
    methods: {
        formSub: function(e) {
            e.preventDefault();
            this.$emit('formSub', this.textForTrans);
        } 
    }
}
</script>

<style>

</style>
