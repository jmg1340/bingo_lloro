<template>
  <q-page >
    <!-- <img alt="Quasar logo" src="~assets/quasar-logo-full.svg"> -->
	<div class="container1">
    <!-- <div class="" style="background-color:lightgreen"> -->

      <div class="numeroSortejat">
        Numero: <span id="numero">{{nouNumero}}</span>
      </div>
      


      <div class="botons">
        
        <q-btn icon="help_outline" color="faded" class="q-ml-lg" @click="opened = true">
          <q-modal v-model="opened">
            <h4>Numeros cantats</h4>
            <jmg_numCantats :numeros="numeros" :posicions="posicionsNumCantats" ></jmg_numCantats>
            <q-btn
              class=""
              color="primary"
              @click="opened = false"
              label="Tanca"
            />
          </q-modal>
        </q-btn>
        
        <q-btn icon="replay" color="faded" class="q-mx-md " @click="fNouNumero"></q-btn>

      </div>


    <!-- </div> -->


    

<!--     <div id="quadreNumeros" class="" style="background-color:lightblue"> -->

      <div class="cartrons cartro1 q-mt-lg">
        <jmg_cartro :numeros="numeros" 
                    min1="1"  max1="5" 
                    min2="11" max2="15" 
                    min3="21" max3="25">
        </jmg_cartro>
      </div>

      <div class="cartrons cartro2 q-mt-lg">
        <jmg_cartro :numeros="numeros" 
                    min1="6"  max1="10" 
                    min2="16" max2="20" 
                    min3="26" max3="30">
        </jmg_cartro>
      </div>

      <div class="cartrons cartro3">
        <jmg_cartro :numeros="numeros" 
                    min1="31" max1="35" 
                    min2="41" max2="45" 
                    min3="51" max3="55">
        </jmg_cartro>
      </div>

      <div class="cartrons cartro4">
        <jmg_cartro :numeros="numeros" 
                    min1="36" max1="40" 
                    min2="46" max2="50" 
                    min3="56" max3="60">
        </jmg_cartro>
      </div>

      <div class="cartrons cartro5">
        <jmg_cartro :numeros="numeros" 
                    min1="61" max1="65" 
                    min2="71" max2="75" 
                    min3="81" max3="85">
        </jmg_cartro>
      </div>

      <div class="cartrons cartro6">
        <jmg_cartro :numeros="numeros" 
                    min1="66" max1="70" 
                    min2="76" max2="80" 
                    min3="86" max3="90">
        </jmg_cartro>
      </div>

<!-- 	  </div> -->


  </div>
  </q-page>
</template>

<style>
  /*.container1{
    display: grid;
    height: 100vh;
  }*/

  .container1 {
    display: grid;
    /*height: 100vh;*/
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 2fr 2fr 2fr;
    grid-template-areas: "numeroSortejat botons" "cartro1 cartro2" "cartro3 cartro4" "cartro5 cartro6";

    align-items: center;
  }


  .numeroSortejat { 
    grid-area: numeroSortejat; 
      text-align: center;
  }

  .botons { 
    grid-area: botons;
    text-align: right;
  }

  .cartro1 { grid-area: cartro1; }

  .cartro2 { grid-area: cartro2; }

  .cartro3 { grid-area: cartro3; }

  .cartro4 { grid-area: cartro4; }

  .cartro5 { grid-area: cartro5; }

  .cartro6 { grid-area: cartro6; }




  .cartrons{
     border: 1px dashed blue;
  }

  #numero{
    font-size: 2em;
    color: blue;
  }


  #quadreNumeros{
    /*border: 1px solid blue;*/
  }
</style>




<script>
import jmg_cartro from "components/cartro";
import jmg_numCantats from "components/numCantats";

export default {
  components:{
  	jmg_cartro,
    jmg_numCantats
  },

  name: 'jmg-linea',

  created () {
    for(var i=0; i < 90; i++){
      this.numeros.push({valor: i + 1, cantat: false});
      this.posicionsNumPendents.push(i);
    }
  },

  data () {
    return {
      numeros: [],
      posicionsNumPendents: [],
      posicionsNumCantats: [],
      nouNumero: null,

      opened: false
    }
  },

  methods:{
    fNouNumero (){
      // sorteig de la posicio de la matriu... i per tant del valor
      var numeroPosicio = Math.floor(Math.random() * this.posicionsNumPendents.length);
      // mostrar el numero sortejat
      this.nouNumero = this.numeros[this.posicionsNumPendents[numeroPosicio]].valor;
      // marcar el numero com a cantat
      this.numeros[this.posicionsNumPendents[numeroPosicio]].cantat = true;
      // eliminar posicio de posicionsNumPendents i afegir-la a posicionsNumCantats (al començament)
      this.posicionsNumCantats.unshift(this.posicionsNumPendents.splice(numeroPosicio,1))
    }
  },


  computed:{

  }
}
</script>
