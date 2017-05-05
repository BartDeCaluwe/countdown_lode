<template>
  <div id="app">
    <h1>Gelukkige verjaardag Marlies!</h1>
    <br>
    <br>
    <br>
    <br>
    <h1 id='countdown'>{{ countdownDate }}</h1>
    <br>
    <br>
    <br>
    <br>
    <h1>{{ message }}</h1>
  </div>
</template>

<script>
import Hello from './components/Hello'
import momentcountdown from 'moment-countdown'
import moment from 'moment'

export default {
  name: 'app',
  components: {
    Hello
  },
  data() {
    return {
      message: 'Tip 1: 4 delen',
      countdownDate: ''
    }
  },

  created: function() {
    this.startTimer()
  },

  computed: {
  },

  methods: {
    startTimer: function() {
      var self = this;
      setInterval(function() {
        self.countdownDate = moment('2017-06-17').countdown().toString();
      }, 1000);
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

#countdown{
  font-size: 4rem;
}
</style>
