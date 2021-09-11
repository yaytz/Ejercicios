<template>
<div class="poke">
<input type="text" placeholder="busca un poke" v-model="busqueda"/>
<input type="button" value="buscar" v-on:click="getPokemon">
  <div v-if="img" >
    <img :src="img">
    <div>{{nombre}}</div>
    <div>{{habilidad}}</div>
  </div>
</div>

</template>

<script>
import axios from 'axios'

export default{
  name: 'poke',
  data(){
    return{
      busqueda: null,
      pokemon: null,
      nombre: null,
      img: null,
      habilidad: null,
    }
  },
  methods:{
  getPokemon:function(){
    axios.get(`https://pokeapi.co/api/v2/pokemon/${this.busqueda}`)
    .then((response)=>{
      this.pokemon=response.data;
      var nombre= response.data.name;
      this.nombre= nombre;
      console.log(this.pokemon);
      //const{name}=response.data;
      const habilidad= response.data.abilities[0].ability.name;
      this.habilidad= habilidad;
      const img= response.data.sprites.front_default;
      this.img=img;
    });
  },

},

};
</script>
