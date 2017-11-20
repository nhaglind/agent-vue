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
      images: ''
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
        images.push('https://www.notebookcheck.net/fileadmin/Notebooks/News/_nc3/20170911_Google_Chrome_logo_vector_download.png');
      }
      if (responseUA.includes("Firefox")) {
        images.push('https://www.underconsideration.com/brandnew/archives/firefox_2017_logo.jpg');
      }
      if (responseUA.includes("Mac")) {
        images.push('https://www.logodesignlove.com/images/classic/apple-logo-rob-janoff-01.jpg');
      }
      if (responseUA.includes("Edge")) {
        images.push('https://png.icons8.com/microsoft-edge/color/1600');
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
