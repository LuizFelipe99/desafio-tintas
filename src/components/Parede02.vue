<template>
  <div class="parede01"> 
    <table border="1px" >
      <tr>
        <td>Parede 01</td>
        <td>Medidas em Metros</td>
      </tr>
      <tr>
        <td>Largura</td>
        <td><input v-model="largura1"  placeholder="Lagura da primeira parede em METROS"></td>
      </tr>
      <tr>
        <td>Altura</td>
        <td><input v-model="altura1"  placeholder="Lagura da primeira parede em METROS"></td>
      </tr>
      <tr>
        <td>Portas</td>
        <td><input v-model="qtePortas"></td>
      </tr>
      <tr>
        <td>Janelas</td>
        <td><input v-model="qteJanelas"></td>
      </tr>
      <tr>
        <td>Qte. Tinta</td>
        <td v-if=" calcAreaParedes " > {{tinta1}} lts </td>
        <td v-else> 0 </td>
      </tr>
      <tr>
        <td><button @click="calcAreaParedes(); calcTinta(); calcPortas();" >Resultado</button></td>
        <td v-if="areaParedes >= 1 & areaParedes <=15 & areas <= (areaParedes/2) & (areas + areaParedes <= 15) "> ÁREA: {{areaParedes + areas}}</td>
        <td v-else>Verifique com atenção suas medidas.</td>
      </tr>
    </table>  
    


    

    
  </div>
</template>

<script>
export default {
  name: 'Parede01',
 data(){
   return{
     //declarei as variaveis utilizadas durante o processo

     largura1: 0.0,
     altura1: 0.00,
     areaParedes: 0.0,
     
     tinta1: 0.0,

     qtePortas: 0,
     qteJanelas: 0,
     areas: 0,    

     mensagem: false
   }
 },
 methods:{
   calcAreaParedes(){
     //verifico se existe alguma porta a ser colocada, se sim adiciono mais 30cm
     if (this.qtePortas >= 1){
       //adiciono mais 30cm no calculo porque existe uma porta
       this.areaParedes =  (this.altura1 * this.largura1) + 0.30
     }else{
       //senao houver porta faz o calculo da area normal
        this.areaParedes =  (this.altura1 * this.largura1) 
     }
   },
   calcTinta(){
     //calcula quantidade de tintas em litros
     this.tinta1 = (this.areaParedes / 5)
   },

   calcPortas(){
     //calcula area de portas e janelas
    this.areas = (this.qtePortas * 1.52) + (this.qteJanelas * 2.40)
   },
   verifica(){
     
   }
 },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>



</style>
