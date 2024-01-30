<template>
  <div class="person">
    <h2>姓名：{{ name }}</h2>
    <h2>年龄：{{ age }}</h2>
    <h2>地址{{ address }}</h2>
    <button @click="changeName">修改名字</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="showTel">查看</button>
    <hr />
  </div>
</template>

<!-- 用来修改文件名字 -->
<!-- <script lang="ts">
export default {
  name: "Person234",
};
</script> -->

<!-- 相当于在setup函数中写了数据和方法 
  setup函数中不可以使用this，this为undefined，vue3中弱化this
-->
<script setup lang="ts" name="Person">
// 数据，原来写在data 中，注意此时name、age、tel不是响应式的
import { ref } from "vue";

//ref创建：基本类型的响应式数据
let name = ref("张三");
let age = ref(18);
let tel = "189563254";
let address = "北京";
// 方法
// 操作ref相关的数据，需要获取ref中value的值
function changeName() {
  name.value = "zhang-3"; //name改了，但是不是响应式的
}
function changeAge() {
  age.value += 1;
}
function showTel() {
  alert(tel);
}
</script>

<style scoped>
.person {
  background-color: skyblue;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}
.button {
  margin: 0 5px;
}
</style>
