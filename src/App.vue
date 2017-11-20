<template>
  <div id="app">
    <p>{{userAgent}}</p>
    <img v-bind:src="browser"><img>
    <img v-bind:src="device"></img>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      userAgent: '',
      browser: '',
      device: ''
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
      if (this.userAgent.includes("Mac")) {
        console.log('Mac!');
        this.device = 'https://www.logodesignlove.com/images/classic/apple-logo-rob-janoff-01.jpg';
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
