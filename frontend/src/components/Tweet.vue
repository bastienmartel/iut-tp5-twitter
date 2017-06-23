<template>
  <div class="Tweet">
    <div>
      <strong> {{ tweet.auteur.nom }} {{ tweet.auteur.prenom }} </strong>
      <a @click="retweet()">
        <span class="handle">@{{tweet.auteur.handle}} -> {{moment(tweet.date).fromNow()}} </span>
      </a>
    </div>
    <div>
      {{tweet.contenu}}
    </div>
    <div>
      <ul>
        <li class="button"><icon name="reply"/> </li>
        <li class="button"><a @click="retweet(tweet.id)"><icon name="retweet"/></a><span>{{tweet.retweeters.length}}</span></li>
        <li class="button"><icon name="heart"/></li>
        <li class="button"><icon name="envelope"/></li>
      </ul>
    </div>
  </div>
</template>

<script>
import moment from 'moment'
import 'vue-awesome/icons'
import Icon from 'vue-awesome/components/Icon'
export default {
  created () {
    moment.locale('fr')
  },
  name: 'tweet',
  props: ['tweet'],
  components: {Icon},
  methods: {
    moment: function (date) {
      return moment(date)
    },
    retweet: function (id) {
      var data = new FormData()
      data.append('utilisateur', 'MeGusta')
      data.append('tweet', id)
      this.$http.post('http://localhost:8080/retweet', data, {responseType: 'text'})
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  li.button {
    display: inline-block;
  }

  a {
    color: #42b983;
  }

  span.handle {
    color: gray;
  }
</style>
