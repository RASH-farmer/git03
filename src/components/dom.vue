<template>
  <div>
    获取DOM
    <h1 id="h" ref="myh">VUE</h1>
    <child ref="myc"></child>
  </div>
</template>

<script>
import Child from "./Child.vue";
export default {
  components: { Child },
  name: "Day07Dom",

  data() {
    return {};
  },

  mounted() {
    console.log(document.getElementById("h"));
    console.log(this.$refs.myh);
    console.log(this.$refs.myc);
    const child = this.$refs.myc;
    child.fn();
    child.msg = "Vue2.0";
    console.log(child.msg);
  },

  methods: {},
};
</script>

<style scoped>
</style>