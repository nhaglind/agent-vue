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
      let responseUA = this.userAgent = navigator.userAgent;
      if (responseUA.includes("Chrome")) {
        console.log('Chrome');
        this.browser = 'https://www.notebookcheck.net/fileadmin/Notebooks/News/_nc3/20170911_Google_Chrome_logo_vector_download.png';
      }
      if (responseUA.includes("Firefox")) {
        console.log('Firefox');
        this.browser = 'https://www.underconsideration.com/brandnew/archives/firefox_2017_logo.jpg';
      }
      if (responseUA.includes("Mac")) {
        console.log('Mac');
        this.device = 'https://www.logodesignlove.com/images/classic/apple-logo-rob-janoff-01.jpg';
      }
      if (responseUA.includes("Edge")) {
        console.log('Edge');
        this.browser = 'https://png.icons8.com/microsoft-edge/color/1600';
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
  margin-top: 150px;
}

img {
  width: 50px;
}

</style>
