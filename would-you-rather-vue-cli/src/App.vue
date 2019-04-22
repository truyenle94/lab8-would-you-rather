<template>
  <div id="app">

    <WouldYouRatherQuestion
            v-for="question in questions"
          v-bind:key="question.id"
          v-bind:question="question.question"
          v-bind:answer1="question.answer1"
          v-bind:answer2="question.answer2"
            v-on:answer-changed="answerChanged">
    </WouldYouRatherQuestion>

      <YouWouldRather
              v-bind:message="userSelectionMessage">
      </YouWouldRather>
  </div>
</template>

<script>
import WouldYouRatherQuestion from './components/WouldYouRatherQuestion.vue'
import YouWouldRather from './components/YouWouldRather.vue'

export default {
  name: 'app',
  components: {
    WouldYouRatherQuestion,
      YouWouldRather
  },
  data() {
    return {
      userSelectionMessage:'',
      questions: [
        {
          id:0,
          question: '...be a detective or a pilot?',
          answer1: 'Be a detective',
          answer2: 'Be a pilot'
        },
        {
          id:1,
          question: '...go skiing or go to a water park?',
          answer1: 'Go skiing',
          answer2: 'Go to a water park'
        },
        {
          id:2,
          question: '...play hide and seek or dodgeball?',
          answer1: 'Play hide and seek',
          answer2: 'Play dodgeball'
        }
      ]
    }
  },
  methods: {
    answerChanged(answer){
        this.userSelectionMessage = `Thanks! You selected ${answer}`
    }

  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
