<template>
  <div id="app">
   <s-main-wrapper> </s-main-wrapper>
  </div>
</template>
<script>

import sMainWrapper from './components/s-main-wrapper';

// API

import api from '@/api.js'
export default {
  name: 'App',
   components:{
    sMainWrapper
   },
    data(){
      return {
        res:[],
        res2:[],
        getResult: []
      }
    },
    async mounted() {
      try {
        const res = await api.get("/albums/1/photos");
        this.res=res
      } catch (err) {
        this.getResult = this.fortmatResponse(err.response?.data) || err;
      }

      api.get("/albums/1/photos").then((response) => {
        this.res2 = response.data
      }).catch((error) => {
        console.log('Show error notification!')
        return Promise.reject(error)
      })
    }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
