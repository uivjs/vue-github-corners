<template>
  <div>
    <github-corners
      :size="size"
      :position="position"
      :color="color"
      :bgColor="bgcolor"
      :bottom="bottom"
      href="https://github.com/uivjs/vue-github-corners"
      zIndex="9999"
      fixed
      target="__blank"
    />
    <header>
      <img alt="Vue logo" src="./assets/logo.png" />
      <a href="https://github.com/ui-vue/vue-markdown-preview" target="__blank">Vue Github Corners</a>
      <p>{{ description }}</p>
      <div class="button">
        <button @click="size = 120">Set Size 120px</button>
        <button @click="size = 80">Set Size 80px</button>
        <button @click="position = 'left'">Left</button>
        <button @click="position = 'right'">Right</button>
        <button @click="bottom = !bottom">{{ bottom ? 'Top' : 'Bottom' }}</button>
      </div>
      <div class="button">
        <button @click="bgcolor = '#F95C2B'" style="background: #f95c2b">Orange #F95C2B</button>
        <button @click="bgcolor = '#28a745'" style="background: #28a745">Green #28a745</button>
        <button @click="bgcolor = '#dc3545'" style="background: #dc3545">Red #dc3545</button>
        <button @click="bgcolor = '#008EF0'" style="background: #008ef0">Blue #008EF0</button>
        <button @click="(color = '#151513'), (bgcolor = '#fff')">Light</button>
        <button @click="(color = '#fff'), (bgcolor = '#151513')" style="background: #151513; color: #fff">Dark</button>
      </div>
    </header>
    <markdown-preview :source="markdown" class="markdown"></markdown-preview>
  </div>
</template>
<script>
import { defineComponent } from 'vue';
import GithubCorners from '@uivjs/vue-github-corners';
import MarkdownPreview from '@uivjs/vue-markdown-preview';
import '@uivjs/vue-markdown-preview/markdown.css';
import str from '@uivjs/vue-github-corners/README.md';
import pkg from '@uivjs/vue-github-corners/package.json';
import './App.css';

export default defineComponent({
  data() {
    return {
      bgcolor: '#151513',
      color: '#fff',
      size: 80,
      bottom: false,
      position: 'right',
      markdown: str,
      description: pkg.description,
    };
  },
  components: {
    GithubCorners,
    MarkdownPreview,
  },
});
</script>

<style scoped>
header {
  text-align: center;
  min-height: calc(100vh - 130px);
  padding-top: 63px;
  padding-bottom: 65px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: calc(10px + 2vmin);
  color: #fff;
}
header img {
  height: 20vmin;
}
header a {
  color: #09d3ac;
  font-weight: bold;
}
header p {
  margin-bottom: 10px;
  padding: 10px;
  max-width: 560px;
  white-space: pre-wrap;
  word-wrap: break-word;
}

.button {
  margin-bottom: 10px;
}
.button button {
  position: relative;
  display: inline-block;
  border: 0 solid;
  border-radius: 2px;
  padding: 5px 10px;
  margin: 0 2px;
  font-size: 12px;
  font-weight: 700;
  text-shadow: 0 1px hsla(0, 0%, 100%, 0.9);
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  cursor: pointer;
  transition: all 0.3s;
}
.button button + button {
  margin-left: 5px;
}
.button button:hover {
  outline: 0;
  box-shadow: 0 0 0 2px rgba(255, 255, 255, 0.38);
}
.button button:focus {
  box-shadow: 0 0 0 2px rgba(255, 255, 255, 0.38);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.markdown {
  margin: 0 auto;
  max-width: 820px;
  margin-bottom: 110px;
  padding: 16px;
  border-radius: 5px;
  background: #fff;
}
</style>
