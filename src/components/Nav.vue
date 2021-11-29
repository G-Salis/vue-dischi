<template>
  <header>
  
   <div class="container">
    <img id="logo" src="../assets/img/spotify.png" alt="">
    <SearchBar/>
   </div>
    
  </header>
</template>

<script>

  import SearchBar from './SearchBar';


  export default {

  name: 'Nav',
  components:{

    SearchBar
    
  },
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