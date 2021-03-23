<template>
  <div class="home">
    <input type="number" v-model="number"> 
    <button @click="click">住所自動入力</button> 
    <p>住所：{{address}}</p>
  </div>
</template>

<script>
import axios from "axios";
  

export default {
  data() {
    return{
      number:"",
      address:"",
    };
  },
  methods:{
    async click(){
     const items = await axios.get(`https://apis.postcode-jp.com/api/v4/postcodes/${this.number}?apiKey=37mFixiujYdg2EkSwSOPMZaOoxNDzOALULABg07`);

     this.address = items.data
    }

  }
  }
  
</script>
