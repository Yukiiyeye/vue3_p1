<template>
  <div :style="{ fontSize: postFontSize + 'em' }">
    <h4>{{ title }}</h4>
    <button @click="$emit('enlarge-text')">Enlarge text</button>
    <button @click="decreaseTextSize">Decrease text</button>
    <button @click="enlargeText">Enlarge only this</button>
  </div>
</template>

<script>
export default {
  props: ['title'],
  data() {
    return {
      postFontSize: 1
    };
  },
  methods: {
    decreaseTextSize() {
      this.postFontSize -= 0.1; // 缩小当前子组件的字体大小
    },
    enlargeText() {
      this.postFontSize += 0.1; // 放大当前子组件的字体大小
    }
  }
}
</script>
