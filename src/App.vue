<template>
  <div id="app">

    <h1> Would you rather...</h1>

    <would-you-rather-1 
    v-bind:question="wyrQuestion"
    v-bind:answer1="wyrAnswer1"
    v-bind:answer2="wyrAnswer2"
    v-on:answer-changed="answerChanged">
    </would-you-rather-1>

    <p>{{ userSelectionMessage }}</p>

  </div>

  
</template>

<script>
import WouldYouRather1 from './components/WouldYouRather1.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather1
  },
  data() {
    return {
      wyrQuestion: 'Would you rather live in a place with a lot of trees or live in a place near the ocean?',
      wyrAnswer1: 'Live in a place with a lot of trees',
      wyrAnswer2: 'Live in a place near the ocean',
      userSelectionMessage: ''
    }
  },
  methods: {
    answerChanged() {
      this.userSelectionMessage= 'Thanks! you chose ${choice}'
    }
  }
}
</script>

<style>

body {
  background: gray ;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background: peachpuff;
}
</style>
