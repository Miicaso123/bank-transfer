<template>
  <div class="transfer">
    <div class="container">
      <div v-if="isMobile" class="page">
        <ConfirmHeader />
        <ConfirmForm />
      </div>

      <div v-else class="nopage">
        <NoPage />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import NoPage from '@/components/NoPage.vue';

const isMobile = ref<boolean>(true);

const checkScreen = () => {
  isMobile.value = window.innerWidth <= 500;
};

onMounted(() => {
  checkScreen();
  window.addEventListener('resize', checkScreen);
});

onUnmounted(() => {
  window.removeEventListener('resize', checkScreen);
});
</script>

<style scoped>
.transfer {
  background: #f9f9f9;
  height: 100vh;
}

.container {
  padding: 16px;
}
</style>
