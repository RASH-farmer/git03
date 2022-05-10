<template>
  <div>
    <!-- axios -->
    <p>获取所有图书信息</p>
    <button @click="getAllFn">获取</button>
    <div class="box2">
      <ul>
        <li v-for="(item, i) in arr" :key="i">
          {{ item.id }}
          <hr />
          {{ item.bookname }}
          <hr />
          {{ item.author }}
          <hr />
        </li>
        <li></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Day07Axios",

  data() {
    return {
      arr: [],
    };
  },
  created() {
    // this.getAllFn();
  },

  mounted() {},

  methods: {
    // getAllFn() {
    //   axios({
    //     url: "http://www.liulongbin.top:3006/api/getbooks",
    //     method: "GET",
    //   }).then((res) => {
    //     console.log(res);
    //     // this.arr = res.data.data;
    //     this.arr.push(res.data.data[this.arr.length]);
    //   });
    // },
    async getAllFn() {
      const res = await this.$axios.get("/api/getbooks");
      console.log(res);
      this.arr = res.data.data;
    },
  },
};
</script>

<style scoped>
</style>
