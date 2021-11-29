<template>
  <div class="album">
   
      <img :src="albums.poster" :alt="albums.title">

      <h4>{{albums.title}}</h4>
      <h5>{{albums.author}}</h5>
      <h5>{{albums.year}}</h5>

    
  </div>
</template>


<script>
export default {
  name: "Album",
  props:{
    albums: Object
  }
}
</script>


<style lang="scss">
.album{
  background-color: #2E3A46;
  display: flex;
  align-items: center;
  flex-direction: column;
  flex-wrap: wrap;
  width: calc((100% - 20px) / 5);
  margin-bottom: 20px;
  padding: 15px;
    
  img{
    width: 100%;
    margin-bottom: 10px;
    object-fit: cover;
    object-position: top;
    }
  }
</style>