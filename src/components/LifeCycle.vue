<template>
  <div class="box1">
    <button @click="fn">按钮</button>
    <hr />
    <span>{{ num }}</span>
    <span class="sp1" id="sp1"> </span>
    <ul id="myul">
      <li v-for="(item, i) in arr" :key="i">{{ item }}------{{ i }}</li>
    </ul>
    <button @click="addFn">添加</button>
  </div>
</template>

<script>
export default {
  name: "Day07LifeCycle",
  data() {
    return {
      num: 0,
      msg: "Hello Vue",
      timer: null,
      arr: [11, 22, 33, 55, 44],
    };
  },
  // 创建阶段
  // new Vue()以后 vue内部给实例对象添加了一些属性和方法，data和methods初始化之前
  beforeCreate() {
    console.log("beforeCreate");
    console.log(this.msg);
  },
  // data和methods初始化以后
  // 场景：网络请求  注册全局事件
  created() {
    console.log("created");
    console.log(this.msg);
    // this.timer = setInterval(() => {
    //   console.log(11);
    // }, 1000);
  },
  // 挂载阶段
  // 真实dom挂载之前
  // 场景  预处理data 不会触发update钩子函数
  beforeMount() {
    console.log("beforeMount");
    console.log(document.getElementById("sp1"));
    this.msg = "挂载";
    // console.log(this.msg);
  },
  // 真实dom挂载以后
  //  场景：使用真实dom
  mounted() {
    console.log("mounted");
    console.log(document.getElementById("sp1"));
  },
  // 更新
  // data数据改变才执行
  // 更新前
  beforeUpdate() {
    console.log("beforeUpdate");
    const temp = document.querySelectorAll("#myul>li").length;
    // console.log(document.getElementById("myul"));
    console.log(temp);
    console.log(document.querySelectorAll("#myul>li")[temp]);
  },
  updated() {
    console.log("update");
    const temp = document.querySelectorAll("#myul>li").length;
    console.log(temp);
    console.log(document.querySelectorAll("#myul>li")[temp - 1]);
  },
  beforeDestroy() {
    console.log("beforeDestroy");
  },
  destroyed() {
    console.log("destroyed");
  },
  methods: {
    fn() {
      this.num++;
      console.log(1);
    },
    addFn() {
      this.arr.push((Math.random() * 100 - 1).toFixed(0));
      console.log("添加");
    },
  },
};
</script>

<style scoped>
</style>