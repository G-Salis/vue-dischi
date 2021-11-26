<template>
  <main>

    <div class="container">
      
        <Album
          v-for="(album, index) in albums"
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