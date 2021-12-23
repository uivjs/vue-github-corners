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
    <svg class="arrow" viewBox="0 0 1024 1024" width="160" height="160">
      <path
        d="M819.103329 271.553343c-43.724084 116.925762-85.260531 200.227804-132.751217 259.863272-23.748923 29.828476-48.965818 53.774322-76.803581 73.230322-27.841343 19.45242-58.328615 34.429315-92.700643 46.183832-8.664615 2.98249-22.073287 5.066294-37.286489 5.048392-24.622545 0.025063-54.075077-5.349147-78.045986-19.137343-12.005147-6.888727-22.656895-15.818294-30.952728-27.214769-8.292252-11.407217-14.293035-25.295664-16.860195-42.485259a73.463049 73.463049 0 0 1-0.809175-10.862993c0.00358-13.412252 3.691413-26.20151 10.229258-38.006154 9.788867-17.694434 26.086937-33.075916 45.331693-43.917426 19.230434-10.859413 41.335944-17.146629 62.370909-17.135888 18.360392 0.007161 35.814937 4.715413 50.387245 15.066405 9.72442 6.881566 17.823329 18.367552 23.390881 32.785902 5.578294 14.393287 8.607329 31.607944 8.600168 49.424112 0.00358 18.00951-3.079161 36.624112-9.495273 53.634686-6.416112 17.021315-16.133371 32.402797-29.327217 44.250405-52.549818 47.200671-107.391105 89.188252-179.099748 123.277427-71.708643 34.082014-160.406378 60.297846-280.672672 75.446601l1.79021 14.210685c121.412028-15.284811 211.735273-41.880168 285.033623-76.72123 73.29835-34.830322 129.45007-77.877706 182.522629-125.558154 15.184559-13.644979 26.069035-31.049399 33.158266-49.853762 7.089231-18.815105 10.415441-39.055217 10.419021-58.686658-0.007161-19.427357-3.254601-38.263944-9.566881-54.594238-6.323021-16.305231-15.725203-30.222322-28.453595-39.291524-17.350713-12.330965-37.898741-17.723077-58.679496-17.712336-31.819189 0.039385-64.42249 12.406154-89.492588 32.581819-12.524308 10.103944-23.168895 22.202182-30.737902 35.850741-7.565427 13.637818-12.026629 28.872503-12.023049 44.948587 0 4.275021 0.315077 8.607329 0.966713 12.97186 2.867916 19.327105 9.799608 35.560727 19.44884 48.8047 14.482797 19.892811 34.855385 32.943441 56.345063 41.006545 21.518322 8.066685 44.253986 11.235357 64.229146 11.242518 16.512895-0.017902 31.081622-2.13393 41.919553-5.818182 35.442573-12.11614 67.233119-27.701706 96.273902-47.995525 43.577287-30.440727 80.856615-71.42221 115.379021-126.703888 34.533147-55.29242 66.395301-124.910098 99.388867-213.113734l-13.426573-5.019748z"
        fill="#8f8f8f"
      ></path>
      <path
        d="M743.040895 344.686993l77.544727-57.802294 13.4767 85.400168a7.160839 7.160839 0 0 0 14.146237-2.230601l-15.324195-97.10814a7.139357 7.139357 0 0 0-4.371693-5.513846 7.142937 7.142937 0 0 0-6.981818 0.891524l-87.050741 64.884364a7.160839 7.160839 0 1 0 8.560783 11.478825z"
        fill="#8f8f8f"
      ></path>
    </svg>
    <header>
      <img alt="Vue logo" src="./assets/logo.png" />
      <a href="https://github.com/uivjs/vue-github-corners" target="__blank">Vue Github Corners</a>
      <p>{{ description }}</p>
      <div class="button">
        <button @click="size = 120">Set Size 120px</button>
        <button @click="size = 80">Set Size 80px</button>
        <button @click="position = position === 'left' ? 'right' : 'left'">
          {{ position === 'left' ? 'Right' : 'Left' }}
        </button>
        <button @click="bottom = !bottom">{{ bottom ? 'Top' : 'Bottom' }}</button>
      </div>
      <div class="button">
        <button @click="bgcolor = '#F95C2B'" style="background: #f95c2b">Orange #F95C2B</button>
        <button @click="bgcolor = '#28a745'" style="background: #28a745">Green #28a745</button>
        <button @click="bgcolor = '#dc3545'" style="background: #dc3545">Red #dc3545</button>
        <button @click="bgcolor = '#008EF0'" style="background: #008ef0">Blue #008EF0</button>
        <button @click="changeTheme" :style="theme === 'dark' ? '' : 'background: #151513; color: #fff;'">
          {{ theme === 'dark' ? 'Light' : 'Dark' }}
        </button>
      </div>
    </header>
    <markdown-preview class="markdown">
      {{ markdown }}
    </markdown-preview>
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

console.log(str);

export default defineComponent({
  data() {
    return {
      theme: 'dark',
      bgcolor: '#151513',
      color: '#fff',
      size: 80,
      bottom: false,
      position: 'right',
      markdown: str,
      description: pkg.description,
    };
  },
  methods: {
    changeTheme() {
      this.theme = this.theme === 'dark' ? 'light' : 'dark';
      if (this.theme === 'dark') {
        this.color = '#fff';
        this.bgcolor = '#151513';
      } else {
        this.color = '#151513';
        this.bgcolor = '#fff';
      }
    },
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
  margin-bottom: 23px;
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

.arrow {
  position: fixed;
  right: 18px;
  top: 32px;
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
