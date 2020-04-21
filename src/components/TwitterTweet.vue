<template lang="html">
  <div class="">
    <img v-bind:src="tweet.img" width="40" height="40" v-bind:title="tweet.name">
    <p>{{tweet.name}} {{tweet.handle}}</p>
    <p>"{{tweet.tweet}}"</p>
    <p>Likes: {{tweet.likes}}</p>
  </div>
</template>

<script>
export default {
  name: 'twitter-tweet',
  props: ['tweet']
}
</script>

<style lang="css" scoped>
</style>
