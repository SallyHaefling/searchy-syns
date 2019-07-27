<template>
  <div id = 'app'>
  <div class = 'header'>
  <div class = 'search'>
    <h1 class = 'title'>Searchy Syns</h1>
    <Search v-on:display-syn="displaySyn" />
  </div>
  </div>
  <SynList v-bind:words='words' />
  </div>
</template>

<script>
import Search from './components/Search'
import SynList from './components/SynList'
import apiKey from '../apiKey'

export default {
  name: 'app',
  components: {
    Search,
    SynList
  },
  data () {
    return {
      key: apiKey,
      words: [],
      error: ''
    }
  },
  methods: {
    async displaySyn (syn) {
      const url=`https://www.dictionaryapi.com/api/v3/references/thesaurus/json/${syn.query}?key=${apiKey}`
      try {
        const data = await fetch(url)
        const words = await data.json()
        this.words = words.map(w => w.meta)
        console.log(words.map(w => w.meta))
      } catch (error) {
        console.log(error.message)
      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  margin-top: 20px;
  display: flex;
  flex-direction: column;
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
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
