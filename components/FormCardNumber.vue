<template>
  <div class="form-card">
    <form class="form">
      <input type="text" placeholder="Name" />
      <input type="number" placeholder="Card number" />
      <input type="number" placeholder="Amount" />
      <input type="number" placeholder="Content" />
      <div class="checkbox-container">
        <input type="checkbox" class="checkbox" />
        <p>Save to directory of beneficiary</p>
      </div>
      <button type="button" @click="toConfirm">Confirm</button>
    </form>
  </div>
</template>

<script setup lang="ts">
const router = useRouter();

const toConfirm = () => {
  router.push('/confirm')
}
</script>

<style scoped>
.form-card {
  margin-top: 35px;
  padding: 16px;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 1px 5px;
  border-radius: 12px;
}

.form {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

input {
  padding: 12px;
  border-radius: 12px;
  border: 1px solid #cacaca;
  font-size: 16px;
  color: #000;
}

input::placeholder {
  color: #cacaca;
}

.checkbox-container {
  display: flex;
  align-items: center;
  gap: 8px;
  color: #979797;
}

.checkbox {
  border: 1px solid #cacaca;
  width: 24px;
  height: 24px;
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
