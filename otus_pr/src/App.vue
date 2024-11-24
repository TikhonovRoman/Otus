<template>
  <Loader v-if="isLoading" />
  <div v-else>
    <div class="container">
      <div class="goods">
        <ICard v-for="product of products" :key="product.id" :product="product"></ICard>
        <div>

        </div>
      </div>
    </div>
  </div>

</template>

<script setup>

import {onMounted, ref } from 'vue';
import ICard from './components/Card.vue';
import Loader from './components/Layout/Loader.vue';

const products = ref([])
const isLoading = ref(true)

onMounted(async () => {
    const res = await fetch('https://fakestoreapi.com/products')
if (res.ok) {
   products.value = await res.json();
   setTimeout(() => {
      isLoading.value = false
    }, "1000");
} else {
  alert("Ошибка: " + res.status);
}
})

</script>

<style scoped>
.container {
  max-width: 1000px;
}

.goods {
  display: grid;
  grid-template-columns: repeat(3, 30%);
  width: 100%;
  max-width: 1000px;
  justify-content: center;
  justify-items: center;
  gap: 30px;
  margin: 0 auto;
}
</style>
