<template>
<div class="Home">

</div>
</template>
<script>
import axios from 'axios'

export default{
  name: 'Home',
  data(){
    return{
      gf: []
    }
  },
  methods:{
    async getGf(){
      const response = await axios.get('https://api.giphy.com/v1/gifs/trending?api_key=nEDtSM1UH5SH7YYGPKdYJG2Q32vE547F&limit=10&rating=g')
      this.gf = response.data
      console.log(this.gf);
    }
  },
  created(){
    this.getGf()
  }
}
</script>
<style scoped>
a {
  color: #10b9be;
}

</style>