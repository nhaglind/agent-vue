<template>
  <div id="app">

    <p>{{userAgent}}</p>
    <img v-for="image in images" :src="image">

  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      userAgent: '',
      images: '',
      imageSource: require(['./assets/images/chrome_logo.png', './assets/images/firefox_logo.png', './assets/images/apple_logo.png', './assets/images/edge_logo.png'])
    }
  },
  created: function () {
    this.displayUA();
    this.imageGrab();
  },
  methods: {
    displayUA: function() {
      this.userAgent = navigator.userAgent
    },
    imageGrab: function() {
      let responseUA = this.userAgent = navigator.userAgent;
      let images = [];
      this.images = images;

      if (responseUA.includes("Chrome")) {
        images.push('./src/assets/images/chrome_logo.png');
      }
      if (responseUA.includes("Firefox")) {
        images.push('./src/assets/images/firefox_logo.png');
      }
      if (responseUA.includes("Mac")) {
        images.push('./src/assets/images/apple_logo.png');
      }
      if (responseUA.includes("Edge")) {
        images.push('./src/assets/images/edge_logo.png');
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
