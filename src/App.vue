<template>
  <div id="app">
    {{msg}}
    <div>
      <input type="text" v-model="info">
      <button @click="handleClick">添加</button>
    </div>
    <ul>
      <!-- 如果报错得添加 :key='item'，默认item没有重复的-->
      <todo-item v-for="item in list" :key="item" >
      <!-- v-slot只能放到template里面使用 -->
      <!-- 使用itemProps接收子组件TodoItem.vue传递的checked -->
      <!-- 作用域插槽使用的场景 -->
          <template v-slot:item='itemProps'>
              <span :style="{fontSize: '20px', color:itemProps.checked ? 'red' : 'green'}">{{item}}</span>
          </template>
      </todo-item>
    </ul>
  </div>
</template>

<script>
//引入组件TodouItem.vue
import TodoItem from "./components/TodoItem";
//注册组件到components下面才可以使用哦
export default {
  name: "app",
  data() {
    return {
      msg: "hello geektime",
      info: "",
      list: []
    };
  },
  methods: {
    //通过@click定义的方法
    handleClick() {
      console.log(1);
      this.list.push(this.info);
      this.info = "";
    }
  },
  components: {
    TodoItem,
  }
};
</script>

<style>

</style>
