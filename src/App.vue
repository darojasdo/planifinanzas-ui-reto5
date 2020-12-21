<template>
  <div id="app">
   
    <h1>Planifinanzas - Modulo de Transacciones</h1>

    <nav>

      <button v-on:click="cambiarTransacciones">Ver Gastos</button>
      <button v-on:click="cambiarAgregarTransaccion">Agregar Gastos</button>
      <button v-on:click="VerIngresos">Ver Ingresos</button>
      <button v-on:click="AgregarIngreso">Agregar Ingreso</button>
      <h2>{{nombre}}</h2>
      
      <router-view></router-view>
    </nav>
    

  </div>
</template>

<script>
import AgregarTransaccion from "./components/AgregarTransaccion";
import VerTransacciones from "./components/VerTransacciones";
import AgregarIngreso from "./components/AgregarIngreso";
import VerIngresos from "./components/VerIngresos";

export default {
  name: 'App',
  components: {AgregarTransaccion, VerTransacciones, AgregarIngreso, VerIngresos},
  data:function(){
    return{
      nombre:2

    };

  },
  methods: {

    cambiarTransacciones: function(){
      if(this.$route.name !="verTransacciones"){
      this.$router.push({name : "verTransacciones"});
      }
    },

    cambiarAgregarTransaccion: function(){
      if(this.$route.name != "agregar"){
      this.$router.push({
        name:"agregar",
        });
      }
    },

    VerIngresos: function(){
      if(this.$route.name !="verIngresos"){
      this.$router.push({name : "verIngresos"});
      }
    },

    AgregarIngreso: function(){
      if(this.$route.name != "agregarIngreso"){
      this.$router.push({
        name:"agregarIngreso",
        });
      }
    }
  },

    beforeCreate: function (){
   
    if(this.$route.name != "verTransacciones"){
    this.$router.push({name:"verTransacciones"});
    }

    
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
