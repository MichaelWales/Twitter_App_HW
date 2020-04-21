<template lang="html">
  <div id="app">
    <link href="https://fonts.googleapis.com/css2?family=Viga&display=swap" rel="stylesheet">

    <header>
      <img src="../src/assets/clipart669455.png" width="175" height="100">
      <h1>T'wit-T'wooer</h1>
      <h3>Total T'wit-T'woos => {{totalTweets}}!</h3>
    </header>

    <div id="filterTweets">
      <h3>Filter by Likes  <input type="number" v-model.number="filterAmount"></h3>
    </div>

    <br>

    <twitter-tweet v-for="(tweet, index) in filteredTweets" :key="index" :tweet="tweet"></twitter-tweet>

  </div>
</template>

<script>
import TwitterTweet from './components/TwitterTweet.vue';
export default {
  name: 'app',
  data() {
    return {
      tweets:[
        {
          id: 1,
          name: 'James',
          handle: '@jokerjames',
          img: 'https://semantic-ui.com/images/avatar2/large/matthew.png',
          tweet: "If you don't succeed, dust yourself off and try again.",
          likes: 10,
        },
        {
          id: 2,
          name: 'Fatima',
          handle: '@fantasticfatima',
          img: 'https://semantic-ui.com/images/avatar2/large/molly.png',
          tweet: "Better late than never but never late is better.",
          likes: 12,
        },
        {
          id: 3,
          name: 'Xin',
          handle: '@xeroxin',
          img: 'https://semantic-ui.com/images/avatar2/large/elyse.png',
          tweet: "Beauty in the struggle, ugliness in the success.",
          likes: 18,
        }
      ],
      filterAmount: 0
    }
  },
  components: {
    'twitter-tweet': TwitterTweet
  },
  computed: {
    totalTweets: function(){
      return this.tweets.reduce((total, tweet) => total + tweet.likes, 0)
    },
    filteredTweets: function(){
      return this.tweets.filter((tweet) => {
        return tweet.likes >= this.filterAmount
      })
    }
  }
}
</script>

<style lang="css" scoped>

header {
  font-family: 'Viga';
}

#filterTweets {
  font-family: 'Viga';
}

#app {
  font-family: 'Viga';
}

</style>
