<template>
  <header class="header">
    <div class="header-back" @click="toTransfer">
      <span><</span>
      <h3>Confirm</h3>
    </div>
  </header>
</template>

<script setup lang="ts">
const router = useRouter();

const toTransfer = () => {
  router.push('/');
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
