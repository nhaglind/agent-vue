<template>
  <div id="app">
    <p>{{userAgent}}</p>
    <img v-bind:src="browser"><img>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'app',
  data () {
    return {
      userAgent: '',
      browser: ''
    }
  },
  created: function () {
    this.displayUA();
    this.browserType();
  },
  methods: {
    displayUA: function() {
      var self = this;
      axios.get('http://httpbin.org/user-agent')
      .then(response => {
        self.userAgent = response.data['user-agent'];
      })
      .catch(error => {
        console.log(error);
      })
    },
    browserType: function() {
      var self = this;
      if ('Mozillasdsada'.includes("Mozilla")) {
        console.log('Mozilla!');
        self.browser = 'https://www.underconsideration.com/brandnew/archives/firefox_2017_logo.jpg';
      }
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
}

img {
  width: 50px;
}

</style>
