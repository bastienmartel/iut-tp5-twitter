<template>
  <div class="Timeline">
    <h1> Bienvenue sur la Timeline ! </h1>
    <ul>
      <li v-for="tweet in tweets">
        <tweet :tweet="tweet"/>
      </li>
    </ul>
  </div>
</template>

<script>
import Tweet from './Tweet'
export default {
  name: 'timeline',
  components: {Tweet},
  data () {
    return {
      tweets: [{auteur: 'Eminem', tweet: 'Mom\'s spaghetti'}, {auteur: 'Obama', tweet: 'Not bad :('}, {auteur: 'Hans', tweet: 'get ze flammenwerfer'}]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: block;
  margin: 0 10px;
}

</style>
