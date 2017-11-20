<template>
  <div id="app">
    <p>{{userAgent}}</p>
    <img v-bind:src="browser"><img>
  </div>
</template>

<script>
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
      this.userAgent = navigator.userAgent
    },
    browserType: function() {
      if (this.userAgent.includes("Mozilla")) {
        console.log('Mozilla!');
        this.browser = 'https://www.underconsideration.com/brandnew/archives/firefox_2017_logo.jpg';
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
