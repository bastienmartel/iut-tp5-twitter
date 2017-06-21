<template>
  <div class="Tweet">
    <h1> Bienvenue sur la Tweetosphère ! </h1>
    <div {{ tweet.auteur }} : {{ tweet.tweet }} </div>
  </div>
</template>

<script>
export default {
  name: 'tweet',
  props: [{auteur: 'Drump', tweet: 'Covfefe'}]
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
