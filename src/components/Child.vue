<template>
  <div>
    <h1>这是Child组件</h1>
  </div>
</template>

<script>
export default {
  name: "Day07Child",

  data() {
    return {
      // msg: "Vue",
    };
  },

  mounted() {},

  methods: {
    fn() {
      console.log("方法被调用了");
    },
  },
};
</script>

<style scoped>
</style>