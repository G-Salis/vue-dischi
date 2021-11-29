<template>
  <div id="app">

    <Nav @selectedType="selectedHeader"/>
    <Main :stringToMain="headerToMain"/>
  
 
  </div>
</template>

<script>

import Nav from "./components/Nav.vue"
import Main from "./components/Main.vue"

export default {
  name: 'App',
  components: {

    Nav,
    Main,
  
  },

   data(){
    return{
    headerToMain: "",
    }
  },
  
  methods:{
    selectedHeader(text){
      this.headerToMain = text;
    }
  },

}
</script>

<style lang="scss">
@import "./assets/style/generals.scss";
@import "./assets/style/utilities.scss";
</style>
