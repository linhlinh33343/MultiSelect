<template>
  <div id="app">
    <MultiSelect :listProvinces="listProvinces" />
  </div>
</template>

<script>

import MultiSelect from './components/MultiSelectPage.vue'
import axios from 'axios'
export default {
  name: 'App',
  data(){
    return {
      listProvinces:[]
    }
  },
  components: {
    MultiSelect
  },
  created(){
       this.getList();
      
    },
  methods: {
    getList() {
            axios.get('https://provinces.open-api.vn/api/?depth=1').then((response) => {
                response.data.map(item=>{
                  
                    this.listProvinces.push(item)
                })
            })
        },
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.wrapper{
  width:480px;
  margin:auto;
}
</style>
