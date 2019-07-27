<template>
  <form class = 'search-form'>
    <input 
      type = 'text' 
      placeholder = 'Type your word to find synonyms!' class = 'search-field'>
    <button class = 'submit-button'>
      submit
    </button>
  </form>
</template>

<script>
</script>

<style scoped>

.search-field {
  border-radius: 5px;
  border: 2px solid hsl(0, 1%, 30%);
  height: 45px;
  width: 250px;
  color: hsl(245, 52%, 82%);
  padding: 6px;
  font-size: 16px;
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

