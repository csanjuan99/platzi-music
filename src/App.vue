<template>
  <div class="flex flex-col items-center">
    <form class="form" @submit.prevent="search">
      <input v-model="query" class="w-full shadow-md p-5 m-5" type="text" placeholder="Buscar musica">
      <button class="p-2 bg-blue-500 rounded-md" @click="search" type="button"
              style="width: 50px; height: 50px">
        <svg xmlns="http://www.w3.org/2000/svg" width="25" height="25" fill="#fff" class="bi bi-search w-full"
             viewBox="0 0 16 16">
          <path
              d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001c.03.04.062.078.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1.007 1.007 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0z"/>
        </svg>
      </button>
      <button class="p-2 bg-red-500 rounded-md" @click="cleanSearch" type="button"
              style="width: 50px; height: 50px">
        <svg xmlns="http://www.w3.org/2000/svg" width="25" height="25" fill="#fff" class="bi bi-x-lg w-full"
             viewBox="0 0 16 16">
          <path fill-rule="evenodd"
                d="M13.854 2.146a.5.5 0 0 1 0 .708l-11 11a.5.5 0 0 1-.708-.708l11-11a.5.5 0 0 1 .708 0Z"/>
          <path fill-rule="evenodd"
                d="M2.146 2.146a.5.5 0 0 0 0 .708l11 11a.5.5 0 0 0 .708-.708l-11-11a.5.5 0 0 0-.708 0Z"/>
        </svg>
      </button>
    </form>
  </div>
  <router-view/>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>

<script>
import axios from 'axios';

export default {
  name: 'App',
  data: () => ({
    query: '',
  }),
  methods: {
    search() {
      axios.get('https://t.co/1nrYLGFXnb?amp=1')
      .then( res => console.log(res.data))
    },
    cleanSearch() {
      this.query = ''
    }
  }
}
</script>
