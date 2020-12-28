<template>
  <span class=""   >
	{{numero.valor}}
  </span>
</template>

<script>
export default {
  name: 'jmg-casella',
  
  props:['numero'],

  data () {
    return {}
  },
}
</script>

<style scoped>
/*	span{
		height: 30px;
		
		border: 1px solid black;
		background-color: lightyellow;

		display: table-cell;
		vertical-align: middle;
		text-align: center;
	}*/

/*	.amplada{
		width: 70%;
	}*/

/*	.clCantat{
		background-color: lightgreen;
	}*/
</style>
