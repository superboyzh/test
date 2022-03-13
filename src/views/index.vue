<template>
  <div id="root">
    <!-- <h2 v-if="a">你好啊</h2> -->
    <h2 :style="{ opacity }">欢迎学习Vue</h2>
    <button @click="stop">点我停止</button>
    <button @click="stop">点我停止</button>
  </div>
</template>

<script>
// import aaa from '../components/button.vue'
  export default {
    // 
  // components:{
  //     aaa
  // },

  data() {
    return {
      // a:false,
      opacity: 1,
    };
  },
  beforeCreate() {
    console.log("beforeCreate");
  },
  created() {
    console.log("created");
  },
  mounted() {
    console.log("mounted", this);
    this.timer = setInterval(() => {
      console.log("setInterval开启了");
      this.opacity -= 0.01;
      if (this.opacity <= 0) this.opacity = 1;
    }, 16);
  },
  methods: {
    stop() {
      this.$destroy();
    },
  },
  beforeDestroy() {
    console.log("beforeDestroy"), clearInterval(this.timer);
  },
};
</script>

<style scoped>
</style>>
