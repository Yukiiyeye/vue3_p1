<!--sy5-->
<template>
  <div>
    <p :style="{ color: textColor, fontSize: fontSize + 'px' }">{{ displayText }}</p>
    <button @click="changeColor">Change Color</button>
    <button @click="changeFontSize">Enlarge Font</button>
    <button @click="changeText">Change Text</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      textColor: 'black',
      fontSize: 16,
      displayText: '阿米诺斯!',
    };
  },
  methods: {
    changeColor() {
      // 生成随机颜色
      this.textColor = getRandomColor();
    },
    changeFontSize() {
      this.fontSize += 2;
    },
    changeText() {
      this.displayText = getRandomText();
    },
  },
};

function getRandomColor() {
  const letters = '0123456789ABCDEF';
  let color = '#';
  for (let i = 0; i < 6; i++) {
    color += letters[Math.floor(Math.random() * 16)];
  }
  return color;
}
function getRandomText(){
  const texts = '福建师范大学是一所历史悠久的大学';
  let textview='';
  for(let i=0;i<15;i++){
    textview += texts[Math.floor(Math.random() * 16)];
  }
  return textview;
}

</script>

<!--1.1-->

<!--<template>-->
<!--  <div>-->
<!--    <div v-if="type === 'A'">A</div>-->
<!--    <div v-else-if="type === 'B'">B</div>-->
<!--    <div v-else-if="type === 'C'">C</div>-->
<!--    <div v-else>Not A/B/C</div>-->

<!--    <h1 v-show="isShow">Hello!</h1>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      type: 'C',-->
<!--      isShow: true,-->
<!--    };-->
<!--  },-->
<!--};-->
<!--</script>-->



<!--2.1-->
<!--<template>-->
<!--  <div>-->
<!--    <ul>-->
<!--      <li v-for="(item, index) in items">-->
<!--        {{ parentMessage }} - {{ index }} - {{ item.message }}-->
<!--      </li>-->
<!--    </ul>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      parentMessage: 'Parent',-->
<!--      items: [{ message: 'Foo' }, { message: 'Bar' }]-->
<!--    };-->
<!--  },-->
<!--};-->
<!--</script>-->

<!--2.2-->
<!--<template>-->
<!--  <div>-->
<!--    <ul>-->
<!--      <li v-for="(value, key, index) in myObject">-->
<!--        {{ index }}. {{ key }}: {{ value }}-->
<!--      </li>-->
<!--    </ul>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      myObject: {-->
<!--        title: 'How to do lists in Vue',-->
<!--        author: 'Jane Doe',-->
<!--        publishedAt: '2016-04-10'-->
<!--      }-->
<!--    };-->
<!--  },-->
<!--};-->
<!--</script>-->

<!--3.1-->
<!--<template>-->
<!--  <div>-->
<!--    <button @click="count++">Add 1</button>-->
<!--    <p>Count is: {{ count }}</p>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      count: 0-->
<!--    };-->
<!--  }-->
<!--}-->
<!--</script>-->

<!--3.2-->
<!--<template>-->
<!--  <div>-->
<!--    <button @click="greet">Greet</button>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      name: 'Vue.js'-->
<!--    };-->
<!--  },-->
<!--  methods: {-->
<!--    greet(event) {-->
<!--      // 方法中的 `this` 指向当前活跃的组件实例-->
<!--      alert(`Hello ${this.name}!`);-->
<!--      // `event` 是 DOM 原生事件-->
<!--      if (event) {-->
<!--        alert(event.target.tagName);-->

<!--      }-->
<!--    }-->
<!--  }-->
<!--}-->
<!--</script>-->

<!--3.3-->
<!--<template>-->
<!--  <div>-->
<!--    <button @click="say('hello')">Say hello</button>-->
<!--    <button @click="say('bye')">Say bye</button>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  methods: {-->
<!--    say(message) {-->
<!--      alert(message);-->
<!--    }-->
<!--  }-->
<!--}-->
<!--</script>-->

<!--4.1-->
<!--<template>-->
<!--  <div>-->
<!--    <input v-model="message" placeholder="edit me" />-->
<!--    <span>Multiline message is:</span>-->
<!--    <p style="white-space: pre-line;">{{ message }}</p>-->
<!--    <textarea v-model="message" placeholder="add multiple lines"></textarea>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->

<!--      message: 'FJNU'-->
<!--    };-->
<!--  }-->
<!--}-->
<!--</script>-->

<!--4.2-->
<!--<template>-->
<!--  <div>-->
<!--    <div>Checked names: {{ checkedNames }}</div>-->

<!--    <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">-->
<!--    <label for="jack">Jack</label>-->

<!--    <input type="checkbox" id="john" value="John" v-model="checkedNames">-->
<!--    <label for="john">John</label>-->

<!--    <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">-->
<!--    <label for="mike">Mike</label>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      checkedNames: []-->
<!--    };-->
<!--  }-->
<!--}-->
<!--</script>-->

<!--4.3-->
<!--<template>-->
<!--  <div>-->
<!--    <div>Picked: {{ picked }}</div>-->

<!--    <input type="radio" id="one" value="One" v-model="picked" />-->
<!--    <label for="one">One</label>-->

<!--    <input type="radio" id="two" value="Two" v-model="picked" />-->
<!--    <label for="two">Two</label>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      picked: 'One'-->
<!--    };-->
<!--  }-->
<!--}-->
<!--</script>-->

<!--4.4-->
<!--<template>-->
<!--  <div>-->
<!--    <p>单选示例</p>-->
<!--    <div>Selected: {{ selected }}</div>-->

<!--    <select v-model="selected">-->
<!--      <option disabled value="">Please select one</option>-->
<!--      <option>A</option>-->
<!--      <option>B</option>-->
<!--      <option>C</option>-->
<!--    </select>-->

<!--    <p>多选示例</p>-->
<!--    <div>Selected: {{ selectedarray }}</div>-->

<!--    <select v-model="selectedarray" multiple>-->
<!--      <option>A</option>-->
<!--      <option>B</option>-->
<!--      <option>C</option>-->
<!--    </select>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      selected: '',-->
<!--      selectedarray: [],-->
<!--    };-->
<!--  }-->
<!--}-->
<!--</script>-->

<!--4.5-->
<!--<template>-->
<!--  <div>-->
<!--    <select v-model="selected">-->
<!--      <option v-for="option in options" :value="option.value">-->
<!--        {{ option.text }}-->
<!--      </option>-->
<!--    </select>-->
<!--    <div>Selected: {{ selected }}</div>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      selected: 'A',-->
<!--      options: [-->
<!--        { text: 'One', value: 'A' },-->
<!--        { text: 'Two', value: 'B' },-->
<!--        { text: 'Three', value: 'C' }-->
<!--      ]-->
<!--    };-->
<!--  }-->
<!--}-->
<!--</script>-->

<!--4.6-->
<!--<template>-->
<!--  <div>-->
<!--    <input ref="input">-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--  mounted() {-->
<!--    this.$refs.input.focus();-->
<!--  }-->
<!--}-->
<!--</script>-->


<!--5.1-->
<!--<template>-->
<!--  <div>-->
<!--    <div :style="{ fontSize: postFontSize + 'em' }">-->
<!--      <BlogPost-->
<!--          v-for="post in posts"-->
<!--          :key="post.id"-->
<!--          :title="post.title"-->
<!--          @enlarge-text="postFontSize += 0.1"-->
<!--      />-->
<!--    </div>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--import BlogPost from '@/views/BlogPost.vue'; // 路径根据你的项目结构进行调整-->

<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      postFontSize: 1,-->
<!--      posts: [-->
<!--        { id: 1, title: 'My journey with Vue' },-->
<!--        { id: 2, title: 'Blogging with Vue' },-->
<!--        { id: 3, title: 'Why Vue is so fun' }-->
<!--      ]-->
<!--    };-->
<!--  },-->
<!--  components: {-->
<!--    BlogPost-->
<!--  }-->
<!--};-->
<!--</script>-->

<!--5.2-->
<!--<template>-->
<!--  <div>-->
<!--    <div :style="{ fontSize: postFontSize + 'em' }">-->
<!--      <BlogPost-->
<!--          v-for="(post, index) in posts"-->
<!--          :key="post.id"-->
<!--          :title="post.title"-->
<!--          @enlarge-text="postFontSize += 0.1"-->
<!--          :index="index"-->
<!--      />-->
<!--    </div>-->
<!--  </div>-->
<!--</template>-->

<!--<script>-->
<!--import BlogPost from '@/views/BlogPost.vue';-->

<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      postFontSize: 1,-->
<!--      posts: [-->
<!--        { id: 1, title: 'My journey with Vue' },-->
<!--        { id: 2, title: 'Blogging with Vue' },-->
<!--        { id: 3, title: 'Why Vue is so fun' }-->
<!--      ]-->
<!--    };-->
<!--  },-->
<!--  components: {-->
<!--    BlogPost-->
<!--  }-->
<!--};-->
<!--</script>-->


