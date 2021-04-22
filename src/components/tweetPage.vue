<template>
  <!-- In the div that contains all my html content, if the isListView key is true, the class will be tweet-container, and the css rules that go with the tweet-container class will display the tweets in list fashion. -->
  <!-- In the div that contains all my html content, if the isListView key is false, the class will be card-container, and the css rules that go with the card-container class will display the tweets in card fashion. -->
  <div
    :class="{ 'tweet-container': isListView, 'card-container': !isListView }"
  >
    <!-- When this button is clicked, the isListView key will be switched either from true to false or from false to true. This button will toggle between list and card view. -->
    <button @click="isListView = !isListView">Switch View</button>
    <!-- Created a div that will be used to contain all my tweets. In the <h3> and <p> tags, I selected from the data array of tweet, then the object, either user, content, or date. -->
    <div v-for="tweet in tweets" :key="tweet.user" class="shadow">
      <h3>{{ tweet.user }}</h3>
      <p>{{ tweet.content }}</p>
      <p>{{ tweet.date }}</p>
    </div>
  </div>
</template>

<!-- Created an array of tweets, with each tweet being an object of key value pairs. Each tweet has a user, content, and date key. -->
<script>
export default {
  name: "tweet-page",
  data: function () {
    return {
      tweets: [
        {
          user: "Joseph",
          content:
            "Must go faster... go, go, go, go, go! Checkmate... We gotta burn the rain forest, dump toxic waste, pollute the air, and rip up the OZONE! 'Cause maybe if we screw up this planet enough, they won't want it anymore! You know what? It is beets. I've crashed into a beet truck.",
          date: "1/2/2021",
        },
        {
          user: "John",
          content:
            "They're using our own satellites against us. And the clock is ticking. God help us, we're in the hands of engineers. You know what? It is beets. I've crashed into a beet truck. What do they got in there? King Kong? You know what? It is beets. I've crashed into a beet truck.",
          date: "1/14/2021",
        },
        {
          user: "Javale",
          content:
            "Jaguar shark! So tell me - does it really exist? Checkmate... God creates dinosaurs. God destroys dinosaurs. God creates Man. Man destroys God. Man creates Dinosaurs. God creates dinosaurs. God destroys dinosaurs. God creates Man. Man destroys God. Man creates Dinosaurs.",
          date: "6/21/2020",
        },
        {
          user: "Barry",
          content:
            "Remind me to thank John for a lovely weekend. I was part of something special. You really think you can fly that thing? Forget the fat lady! You're obsessed with the fat lady! Drive us out of here! Hey, you know how I'm, like, always trying to save the planet? Here's my chance.",
          date: "3/24/2019",
        },
        {
          user: "Rick",
          content:
            "I gave it a cold? I gave it a virus. A computer virus. Just my luck, no ice. Do you have any idea how long it takes those cups to decompose. My dad once told me, laugh and the world laughs with you, Cry, and I'll give you something to cry about you little bastard!",
          date: "8/11/2018",
        },
      ],
      isListView: true,
    };
  },
};
</script>

<style scoped>
.tweet-container {
  display: grid;
  justify-items: start;
  width: 80vw;
  border-bottom: 1px solid black;
}

.shadow {
  box-shadow: 3px 3px 3px black;
}

.card-container {
  display: grid;
  justify-items: center;
  align-items: center;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}
</style>