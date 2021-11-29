<template>
  <header>
  
   <div class="container">
    <img id="logo" src="../assets/img/spotify.png" alt="">
    <SearchBar
    @selectionType="getGen" />
   </div>
    
  </header>
</template>

<script>

  import SearchBar from './SearchBar';


  export default {

  name: 'Nav',
  components:{

    SearchBar,
    
  },
  data(){
    return{
      selection : "",
    }
  },
  methods:{
   getGen(text){
      this.selection = text;
      return this.$emit("selectedType",this.selection);
    }
  },
  computed:{
     
  }
}
</script>



<style lang="scss" >
  header{
    background-color: #2E3A46;
    height: 70px;
  }

  #logo{
    width: 70px;
    height: 70px;
  }
</style>