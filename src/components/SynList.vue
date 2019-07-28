<template>
  <div class = 'synlist-container'>
      <div v-bind:key='word.id' v-for='word in words' class='words-syns-holder'>
        <p class = 'word'>{{ word.id }}</p>
        <p class = 'synonyms-title'>Synonyms:</p> 
        <p class = 'synonyms-text'>
        {{ 
          word.syns.reduce((acc, currSyn, index) => {
            if(currSyn !== ',') {
              return currSyn.join(' ')
            } 
            acc += currSyn
            return acc
          }, '')
        }} 
        </p>
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
  display: flex;
}

.synlist-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.words-syns-holder {
  border-radius: 3px;
  background-color: hsl(255, 17%, 65%);
  box-shadow: 5px 5px 5px hsl(0, 3%, 14%);
  padding: 10px;
  margin: 20px;
  height: 300px;
  width: 400px;
  margin: 30px;
}

.synonyms-title {
    padding-left: 10px;
}

.synonyms-text {
  font-style: italic;
  padding-left: 10px;
}

.synonyms-text:hover {
  cursor: pointer;
}

</style>