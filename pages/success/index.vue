<template>
  <div class="success">
    <div class="container">
      <div v-if="isMobile" class="page">
        <ConfirmHeader />
        <div class="success-content">
          <img src="/images/success.png" alt="success" />
          <div class="success-text">
            <h3>Transfer successful!</h3>
            <p>You have successfully transferred<b> $1,000</b> to <b>Amanda</b>!</p>
          </div>
          <button>Confirm</button>
        </div>
      </div>

      <div v-else class="nopage">
        <NoPage />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
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
.success {
  background: #f9f9f9;
  height: 100vh;
}

.container {
  padding: 16px;
}

.success-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 14px;
}

.success-text {
  width: 80%;
}

.success-text p {
  line-height: 1.4;
}

.success-text h3 {
  color: #3629b7;
}

.success-text b:nth-child(1) {
  color: red;
}

.success-text b:nth-child(2) {
  color: #3629b7;
}

button {
  width: 100%;
  padding: 12px;
  border-radius: 8px;
  border: none;
  font-size: 16px;
  background: #f2f1f9;
  color: white;
}

button:active {
  background: #3629b7;
}
</style>
