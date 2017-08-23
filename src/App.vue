<template>
  <div id="app">
    <picture-input 
          ref="pictureInput" 
          @change="onChange" 
          width="200" 
          height="200" 
          margin="16" 
          accept="image/jpeg,image/png" 
          size="10" 
          buttonClass="btn"
          :removable="true"
          :customStrings="{
            upload: '<h1>Bummer!</h1>',
            drag: 'Drag a 😺 GIF or GTFO'
          }">
        </picture-input>  
  </div>
</template>

<script>
import PictureInput from 'vue-picture-input'

export default {
  name: 'app',
  data () {
    return {
    }
  },
  components: {
    PictureInput
  },
  methods: {
    onChange () {
      console.log('New picture selected!')
      if (this.$refs.pictureInput.image) {
        console.log('Picture loaded.')
      } else {
        console.log('FileReader API not supported: use the <form>, Luke!')
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
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
