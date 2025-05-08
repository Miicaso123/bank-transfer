<template>
  <header class="header">
    <div class="header-back" @click="goBack">
      <span><</span>
      <h3>Transfer</h3>
    </div>
  </header>
</template>

<script setup lang="ts">
const goBack = () => {
  window.parent.postMessage({ type: 'CLOSE_IFRAME' }, '*');
};
</script>

<style scoped>
.header-back {
  display: flex;
  align-items: center;
  gap: 16px;
  font-weight: bold;
}
</style>
