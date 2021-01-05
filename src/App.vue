<template id="app">
  <div >
    <pre>{{ words }}</pre>
  </div>
</template>

<script>
// const test = `paper boi\n paper boi\n gotta\n get\n dat\n paper \t\tboi`;
import test from './assets/bo2k.js';
const source = test.split(" ");

export default {
  name: 'App',
  data() {
    return {
      index: 0,
      words: "",
      source: `paper boi\n paper boi\n gotta\n get\n dat\n paper \t\tboi`,
    };
  },
  mounted() {
    window.addEventListener("keypress", () => {
      if (this.index < source.length) {
        const newWord = source[this.index];
        this.words += ` ${newWord}`;
        this.index += 1;

        window.scrollTo(0, document.body.scrollHeight || document.documentElement.scrollHeight);

      }
    });
  },
}
</script>

<style>
body { 
  margin: 0 !important;
  background: #000000;
  padding: 0 !important; 
  font-size: 1.25em;
}

#app {
  margin: 0em 0em 0em 0em;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #41FF00;
}
</style>
