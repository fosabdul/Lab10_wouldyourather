<template>
<!-- any writing here will show the app display -->
  <div id="app">

    <!-- v-bind to prop name in component
Value is data in this component
 -->
    <would-you-rather v-bind:question="wyrQuestion"
      v-bind:answer1="wyrAnswer1"
      v-bind:answer2="wyrAnswer2"
      v-on:answer-changed="answerChanged"></would-you-rather>

    <p>{{ userSelectionMessage }}</p>
    

    
    
   
  </div>
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'
export default {
  name: 'App',
  components: {
    WouldYouRather
  },// data needs to be a function that returns the component's data 

  data() {
    return {
      wyrQuestion: ' Would you rather ride a camel or ride a horse?',
      wyrAnswer1: 'Ride a Camel',
      wyrAnswer2: 'Ride a Horse',
      userSelectionMessage: ''
    }
  },
  methods: {
    answerChanged(choice) {
      this.userSelectionMessage = `Thanks! You chose ${choice}`
    }
  }
}
</script>

<style>
body {
  background: rgb(181, 181, 165);
} 
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(29, 26, 26);
  margin: 60px;
  padding: 60px;
  margin-top: 40px;
  background: rgb(179, 225, 196);
}
p {
  font-style: italic;
}
</style>