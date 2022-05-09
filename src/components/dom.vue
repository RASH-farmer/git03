<template>
  <div>
    获取DOM
    <h1 id="h" ref="myh">VUE</h1>
  </div>
</template>

<script>
export default {
  name: "Day07Dom",

  data() {
    return {};
  },

  mounted() {
    console.log(document.getElementById("h"));
    console.log(this.$refs.myh);
  },

  methods: {},
};
</script>

<style scoped>
</style>