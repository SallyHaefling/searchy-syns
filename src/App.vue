<template>
  <div id = 'app'>
  <div class = 'header'>
  <div class = 'search'>
    <h1 class = 'title'>Searchy Syns</h1>
    <Search v-on:display-syn="displaySyn" />
  </div>
  </div>
  </div>
</template>

<script>
import Search from './components/Search'
import apiKey from '../apiKey'

export default {
  name: 'app',
  components: {
    Search
  },
  data () {
    return {
      key: apiKey,
      syns: []
    }
  },
  methods: {
    async displaySyn (syn) {
      const url=`https://www.dictionaryapi.com/api/v3/references/thesaurus/json/word?key=${apiKey}`
      try {
        const data = await fetch(url)
        const syns = await data.json()
        this.syns = syns.results
      } catch (error) {
        console.log(error)
      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  margin-top: 20px;
}

.header {
  display: flex;
}

.title {
  font-size: 40px;
  display: flex;
  color: hsl(241, 81%, 64%);
}

.search {
  padding-left: 30px;
}
</style>
