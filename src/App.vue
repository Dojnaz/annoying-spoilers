<template>
  <div id="app">
    <h1>Be like Torn, annoying</h1>
    <textarea
      playerholder="Input"
      v-model="input"
      :style="{
        height: '150px',
        width: '100%',
        maxWidth: '490px',
        minWidth: '100px'
      }"
      :maxlength="nitro ? max / 2.5 : max / 5"
    ></textarea>
    <div :style="{
      display: 'flex',
      width: '500px',
      marginLeft: 'auto',
      marginRight: 'auto'
    }">
      <div><input type="checkbox" v-model="nitro" id="nitro1" /><label for="nitro1">Nitro?</label></div>
      <div :style="{
        marginLeft: 'auto'
      }"></div>
      <div>{{input.length}}/{{nitro ? max / 2.5 : max / 5}}</div>
    </div>
    <br />
    <textarea
      playerholder="Output"
      v-model="output"
      readonly
      :style="{
        height: '150px',
        width: '100%',
        maxWidth: '490px',
        minWidth: '100px',
      }"
    ></textarea>
    <div :style="{
      display: 'flex',
      width: '500px',
      marginLeft: 'auto',
      marginRight: 'auto'
    }">
      <div><input type="checkbox" v-model="nitro" id="nitro2" /><label for="nitro2">Nitro?</label></div>
      <div :style="{
        marginLeft: 'auto'
      }"></div>
      <div>{{output.length}}/{{nitro ? max * 2 : max}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      input: "",
      output: "",
      max: 2000,
      nitro: false
    };
  },
  watch: {
    input(newState) {
      this.output = newState
        .split("")
        .map((part) => `||${part}||`)
        .join("");
    },
  },
};
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
