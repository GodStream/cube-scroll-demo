<template>
  <div id="app">
    <cube-scroll class="scroll-demo">
      <div class="demo-image-wrapper">
        <img class="iamge" alt="Vue logo" src="./assets/logo.png">
      </div>
      <div class="demo-image-wrapper">
        <img class="iamge" alt="Vue logo" src="./assets/logo.png">
      </div>
      <div class="demo-image-wrapper">
        <img class="iamge" alt="Vue logo" src="./assets/logo.png">
      </div>
      <cube-scroll
        class="horizontal-container"
        direction="horizontal"
        :options="{ eventPassthrough: 'vertical' }"
        :data="scrollData">
        <div class="horizontal">
          <div class="horizontal-box" v-for="(item, index) in scrollData" :key="index" @click="onClick(item)">
            <div class="demo-image-wrapper">
              <img class="iamge" alt="Vue logo" src="./assets/logo.png" />
            </div>
            <span>{{ item }}</span>
          </div>
        </div>
      </cube-scroll>
      <div class="demo-image-wrapper">
        <img class="iamge" alt="Vue logo" src="./assets/logo.png">
      </div>
    </cube-scroll>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

const scrollData = [
  '😀 😁 😂 🤣 😃 😄 ',
  '🙂 🤗 🤩 🤔 🤨 😐 ',
  '😔 😕 🙃 🤑 😲 ☹️ ',
  '🐣 🐣 🐣 🐣 🐣 🐣 ',
  '🐥 🐥 🐥 🐥 🐥 🐥 ',
  '🤓 🤓 🤓 🤓 🤓 🤓 ',
  '🦔 🦔 🦔 🦔 🦔 🦔 ',
  '🙈 🙈 🙈 🙈 🙈 🙈 ',
  '🚖 🚖 🚖 🚖 🚖 🚖 ',
  '✌🏻 ✌🏻 ✌🏻 ✌🏻 ✌🏻 ✌🏻 '
]

export default {
  name: 'app',
  components: {
    HelloWorld
  },
  data () {
    return {
      scrollData
    }
  },
  methods: {
    onClick (item) {
      console.log(item)
    }
  }
}
</script>

<style lang="scss">
.scroll-demo {
  height: 100vh;
}
.demo-image-wrapper {
  height: 300px;
  text-align: center;
  .iamge {
    height: 100%;
  }
}
.horizontal-container {
  .cube-scroll-content {
    display: inline-block;
  }
  .horizontal {
    white-space: nowrap;
    display: inline-block;
  }
  .horizontal-box {
    display: inline-block;
  }
  .demo-image-wrapper {
    height: 100px;
    width: 200px;
    .iamge {
      height: 100%;
      width: 100%;
      display: block;
    }
  }
}
</style>
