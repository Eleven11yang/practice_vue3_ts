<template>
  <div class="car">
    <h2>一辆{{ car.brand }}车，价值{{ car.price }}万</h2>
    <button @click="changePrice">修改汽车价格</button>
    <button @click="changeBrand">修改汽车品牌</button>
    <button @click="changeCar">修改汽车</button>
    <h2>当前求和:{{ sum }}</h2>
    <button @click="changeSum">点我sum加一</button>
  </div>
</template>

<!-- 相当于在setup函数中写了数据和方法 -->
<script setup lang="ts" name="Car">
import { ref, reactive } from "vue";
let car = reactive({
  brand: "奔驰",
  price: 100,
});
let sum = ref(0);

//  15集
function changePrice() {
  car.price += 10;
}

function changeSum() {
  sum.value += 1;
}

function changeBrand() {
  car.brand = "宝马";
}

function changeCar() {
  Object.assign(car, {
    brand: "奥拓",
    price: 1,
  });
}
</script>

<style scoped></style>
