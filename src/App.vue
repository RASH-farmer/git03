<template>
  <div>
    <life-cycle v-if="show"></life-cycle>
    <button @click="show = false">-</button>
    <axios></axios>
    <dom></dom>
  </div>
</template>

<script>
import Axios from "./components/axios.vue";
import Dom from "./components/dom.vue";
import LifeCycle from "./components/LifeCycle.vue";
export default {
  components: { LifeCycle, Axios, Dom },
  data() {
    return {
      show: true,
    };
  },
};
</script>

<style scoped>
</style>