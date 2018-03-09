<template>
  <div id="output-app">
      <ul class="out">
        <li><h3 class="result">{{ translated }}</h3></li>
      </ul>
  </div>
</template>


<script>


export default {
    
    props: ['translated'],

}
</script>

<style>
.out {
    list-style-type: none;
}
.result {
    color : royalblue; 
}
</style>