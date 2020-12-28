<template>
	<div class="q-ma-sm col-3 requadre" 
		 :class="{clSeleccionat: seleccionat}" 
		 @click="seleccionat = !seleccionat" 
		 >
	  <jmg_linia :numeros="numeros" :min="min1" :max="max1"></jmg_linia>
	  <jmg_linia :numeros="numeros" :min="min2" :max="max2"></jmg_linia>
	  <jmg_linia :numeros="numeros" :min="min3" :max="max3"></jmg_linia>
	</div>
</template>

<script>
import jmg_linia from "components/linea";

export default {
  components:{
  	jmg_linia
  },
  // name: 'ComponentName',
  props:[
  	'numeros',
  	'min1',
  	'max1',
  	'min2',
  	'max2',
  	'min3',
  	'max3',
  ], 

  data () {
    return {
    	seleccionat: false
    }
  }
}
</script>

<style>
  .requadre{
    border: 3px solid black;
  }
  .clSeleccionat{
    border: 3px solid red;
  }


</style>
