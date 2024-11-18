<template>
    <button class="button">{{props.text}}</button>
</template>

<script setup>
 const props = defineProps({
    text:''
 })
</script>

<style scoped>

.button {
  display: block;
  width: 100%;
  font-weight: 400;
  font-size: 17px;
  color: #70c05b;
  padding: 10px;
  text-align: center;
  border: 1px solid #70c05b;
  border-radius: 4px;
  cursor: pointer;
  transition: 0.2s;
  margin-top: auto;
}

.button:hover {
  border: 1px solid #52ff33;
  background-color: #98f6b9;
  color: #fff;
}
</style>