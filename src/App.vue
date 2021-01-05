<template>
  <div id="app">
    <pre>{{ words }}</pre>
  </div>
</template>

<script>
const test = `paper boi\n paper boi\n gotta\n get\n dat\n paper \t\tboi`;
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
      }
    });
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
