<template>
  <form @submit = 'searchWords' class = 'search-form'>
    <input 
      type = 'text'
      v-model = 'query' 
      name = 'query'
      placeholder = 'Type your word to find synonyms!' class = 'search-field'>
    <button class = 'submit-button'>
      submit
    </button>
  </form>
</template>
<script>
export default {
  name: 'Search',
  data () {
    return {
      query: '',
      id: 1
    }
  },
  methods: {
    searchWords (event) {
      event.preventDefault()
      const syn = {
        query: this.query
      }
      this.$emit('display-syn', syn)
    }
  }
}
</script>

<style scoped>

.search-field {
  border-radius: 5px;
  border: 2px solid hsl(0, 1%, 30%);
  height: 45px;
  width: 250px;
  padding: 6px;
  font-size: 16px;
  margin-left: 500px;
}

.submit-button {
  border-radius: 5px;
  border: 2px solid hsl(0, 1%, 30%);
  cursor: pointer;
  font-size: 16px;
  height: 60px;
  width: 100px;
  margin: 10px;
}
</style>

