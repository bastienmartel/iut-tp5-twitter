<template>
  <div class="Timeline">
    <h1> ME GUSTA Timeline ! </h1>
    <div v-if="loading">Chargement des tweets en cours...</div>
    <div v-else><feed :tweets="tweets"/></div>
  </div>
</template>

<script>
import Feed from './Feed'
import Vue from 'vue'
import Resource from 'vue-resource'
Vue.use(Resource)

export default {
  name: 'timeline',
  components: {Feed},
  data () {
    return {
      tweets: [],
      loading: true
    }
  },
  methods: {
    fetchTweets: function () {
      this.$http.get('http://localhost:8080/list').then(response => {
        this.tweets = response.body
        this.loading = false
        console.log(response.body)
      }, response => {
        this.loading = true
      })
    }},
  retweet: function (id) {
    this.fetchTweets()
  },
  created () {
    this.fetchTweets()
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
