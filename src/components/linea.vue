<template>
  <!-- <div class="grid row no-wrap justify-center"> -->
  <div class="container_linea">
	  <div
      v-for="numero in numeros" 
      v-if="numero.valor >= min && numero.valor <= max"
      class="casella"
      :class="{clCantat: numero.cantat}"
      >
	  	<jmg_casella :numero="numero" class="col-1"></jmg_casella>
	  </div>
  </div>
</template>

<script>

import jmg_casella from "components/casella";

export default {
  components:{
  	jmg_casella
  },

  props:[
  	'numeros',
  	'min',
  	'max'
  ], 

  // name: 'ComponentName',

  data () {
    return {
    }
  },

}
</script>

<style>
  .container_linea {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    grid-template-rows: 1fr ;

    align-items: center;
  }

  .casella{
    border: 1px solid black;
    text-align: center
  }

  .clCantat{
    background-color: lightgreen;
  }  

</style>
