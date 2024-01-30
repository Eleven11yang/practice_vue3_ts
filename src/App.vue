<template>
  <!-- 结构 -->
  <!-- vue3中可以写多个根标签 -->
  <Person />
  <Car />
</template>

<script lang="ts">
import Person from "./components/Person.vue";
import Car from "./components/Car.vue";

export default {
  name: "App", //组件名字
  components: { Person, Car }, //注册组件
};
</script>
