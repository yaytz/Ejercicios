<template>
<div class="poke">
<input type="text" placeholder="busca un poke" />
  <div v-for="(data, index) in pokemon" :key="index"></div>
  <v-img
  class="pointer"
  :src="img"
  height="200" 
  ></v-img>
  <v-card-title>{{pokemon.name}}</v-card-title>
  
</div>

</template>

<script>
import axios from 'axios'

export default{
  name: 'poke',
  data(){
    return{
      pokemon: [],
      polkemons:{
        name:"",
        img:""
      }
        
    }
  },
  methods:{
  getPokemon(){
  const axiosInstance= axios.create({
    headers:{ 
      "Access-Control-Allow-Origin": "*"
    },
   function next() {
      
   }
  });
  
 ('https://pokeapi.co/api/v2/pokemon?offset=0&limit=20')
next null
back null
ArrayB
arra



  .then(response=>{
    this.pokemon=response.data
    console.log(this.pokemon)
    const{name, base_experience}=response.data
    //console.log(name)
    //console.log(base_experience)
    const habilidades=response.data.abilities
    //console.log(habilidades)
    const habilidad= response.data.abilities[1].ability.name
    //console.log(habilidad)
    const img= response.data.sprites.front_default
    //console.log(img) 
  })
  }
 },
 created(){
   this.getPokemon()
 }
}
</script>


