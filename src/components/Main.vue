<template>
  <main>

    <div class="container">
      
        <Album
          v-for="(album, index) in filterAlbum"
          :key="index"
          :albums="album"
        />
        
      
    </div>

  </main>

</template>

<script>


import axios from 'axios';
import Album from './Album';

export default {

  name: 'Main',
  components:{

    Album
    
  },
   props:{
    stringToMain: String,
   },

  data(){
    return{
      albums: [],
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music'
    }
  },

  methods:{
    getApi(){
      axios.get(this.apiUrl)
        .then( r => {
          this.albums = r.data.response;
        })
        .catch( e => {
          console.log(e);
        })
    }
  },

  mounted(){
    this.getApi();
  },
  
  computed:{
    filterAlbum(){
      if (this.stringToMain === "" || this.stringToMain === "all"){
        return this.albums;
      }else{
        let albumsFiltered =[];
        for(let i = 0; i < this.albums.length -1 ; i++){
          if (this.albums[i].genre.toUpperCase().includes(this.stringToMain.toUpperCase())){
          albumsFiltered.push(this.albums[i]);
          }
        }
        return albumsFiltered;
      }
    }
  }
}

</script>

<style lang="scss">

  main{
    background-color: #1E2D3B;
    height: calc(100vh - 70px);
    padding: 40px 0px;
  }
</style>