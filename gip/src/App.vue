<template>
<div class="Home">
  <img v-for="ima in imm" :key="ima.id" :src="ima" alt="cat">
</div>
</template>
<script>
import axios from 'axios'

export default{
  name: 'Home',
  data(){
    return{
      gf: [],
      imm:[]
    }
  },
  methods:{
    async getGf(){
      const response = await axios.get('https://api.giphy.com/v1/gifs/trending?api_key=nEDtSM1UH5SH7YYGPKdYJG2Q32vE547F&limit=10&rating=g')
      this.gf = response.data
      for(let i=0; i<10; i++){
        this.imm[i]=this.gf.data[i].images.downsized.url
      }
      console.log(this.gf);
      //revisar array map, for each, usar un try catch
    }
  },
  created(){
    this.getGf()
  }
}
</script>
