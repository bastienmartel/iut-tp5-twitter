<template>
  <div class="Tweet">

    <div> {{tweet.auteur.handle}} - Nom : {{ tweet.auteur.nom }} ; Prénom : {{ tweet.auteur.prenom }} ; Tweet : {{tweet.contenu}} </div>
  </div>
</template>

<script>
export default {
  name: 'tweet',
  props: ['tweet']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
