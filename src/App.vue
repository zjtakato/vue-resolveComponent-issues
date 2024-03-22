<script setup>
import { h, render, resolveComponent } from 'vue';

function createNotify() {
  const container = document.createElement('div');
  const vnode = h({
    render() {
      const ElBtn = resolveComponent('el-button');
      console.log(ElBtn); // is 'el-button' string, not vnode
      return h(ElBtn, { type: 'primary' });
    },
  });
  render(vnode, container);
}
</script>

<template>
  <el-button @click="createNotify">create notify</el-button>
</template>

<style scoped></style>
