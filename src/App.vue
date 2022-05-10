<template>
  <div>
    <life-cycle v-if="show"></life-cycle>
    <button @click="show = false">-</button>
    <axios></axios>
    <dom></dom>
    <update-dom></update-dom>
  </div>
</template>

<script>
import Axios from "./components/axios.vue";
import Dom from "./components/dom.vue";
import LifeCycle from "./components/LifeCycle.vue";
import UpdateDom from "./components/UpdateDom.vue";
export default {
  components: { LifeCycle, Axios, Dom, UpdateDom },
  data() {
    return {
      show: true,
    };
  },
};
</script>

<style scoped>
</style>