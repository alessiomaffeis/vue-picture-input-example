<template>
  <div id="app">
    <h1>vue-picture-input Example</h1>
    <br /><br />
    <PictureInput
      ref="pictureInput"
      @change="onChange"
      width="600"
      height="600"
      margin="16"
      accept="image/jpeg,image/png"
      size="10"
      :removable="true"
      :customStrings="{
        upload: '<h1>Bummer!</h1>',
        drag: 'Drag a 😺 GIF or GTFO',
      }"
    >
    </PictureInput>
    <br /><br />
    <a
      href="https://github.com/alessiomaffeis/vue-picture-input"
      class="btn btn-success"
      >View project on GitHub</a
    >
  </div>
</template>

<script setup>
import { ref } from "vue";
import PictureInput from "vue-picture-input";

const pictureInput = ref(null);
const image = ref(null);

function onChange(newImage) {
  console.log("New picture selected!");
  if (newImage) {
    console.log("Picture loaded.");
    image.value = newImage;
  } else {
    console.log("FileReader API not supported: use the <form>, Luke!");
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1,
h2 {
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
