<template>
  <div class = 'synlist-container'>
      <div v-bind:key='word.id' v-for='word in words' class='words-syns-holder'>
        <p class = 'word'>{{ word.id }}</p>
        <p class = 'synonyms'>Synonyms: {{ word.syns.flat() }} </p>
      </div>
    </div>
</template>

<script>
export default {
  name: 'SynList',
  props: ['words']
}
</script>

<style scoped>

.word {
  font-size: 24px;
  font-weight: bold;
  padding: 10px;
}

.synlist-container {
  border-radius: 3px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
 
}

.words-syns-holder {
  background-color: hsl(254, 20%, 62%);
  padding: 10px;
  margin: 20px;
  height: 300px;
  width: 400px;
  margin: 30px;
}

.synonyms {
  display: flex;
  flex-direction: column;
}

</style>