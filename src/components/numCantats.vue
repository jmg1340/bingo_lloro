<template>
  <div class="row">
	  <div v-for="posicio in posicions">
	  	<!-- <jmg_casella :numero="numeros[posicio]"></jmg_casella> -->
	  	<q-chip class="bg-warning">{{numeros[posicio].valor}}</q-chip>
	  </div>
  </div>
</template>

<script>


export default {

  props:[
  	'posicions',
  	'numeros',
  ], 

  // name: 'ComponentName',

  data () {
    return {
    	//numeros: [1,2,3,4,5,6,7,8,9,10]
    }
  },

  computed:{

  }
}
</script>

<style>
</style>
