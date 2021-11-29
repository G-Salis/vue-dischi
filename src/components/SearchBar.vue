<template>
 
   <select class="search" name= "search">
    <option value="all">Seleziona Genere</option>
    <option value="rock">rock</option>
    <option value="pop">pop</option>
    <option value="jazz">jazz</option>
    <option value="metal">metal</option>
   </select>

</template>

<script>
export default {
  name: 'SearchBar',
  data(){
    return{
      textToSearch: ''
    }
  },
  methods:{
    reset(){
      this.textToSearch = '';
      this.$emit('sendSearch',this.textToSearch);
    }
  }
}
</script>

<style lang="scss">
.search{
  color: black;
  height: 30px;
  width: 50%;
  margin-top: 22px;

  option{
     background-color: #2E3A46;
  }
}
</style>