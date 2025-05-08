<template>
  <div class="form-card">
    <div class="header">
      <p>Confirm transaction information</p>
    </div>
    <form class="form">
      <label for="1">From</label>
      <input id="1" type="number" />

      <label for="2">To</label>
      <input id="2" type="text" />

      <label for="3">Card number</label>
      <input id="3" type="number" />

      <label for="4">Transaction fee</label>
      <input id="4" type="number" />

      <label for="5">Content</label>
      <input id="5" type="text" />

      <label for="6">Amount</label>
      <input id="6" type="number" />

      <div class="getotp">
        <input type="number" placeholder="OTP" />
        <button class="button-getotp">Get OTP</button>
      </div>
      <button class="button-confirm">Confirm</button>
    </form>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
.form-card {
  padding: 0px 16px;
}

.header p {
  font-size: 12px;
  font-weight: 600;
  color: #979797;
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

label {
  font-size: 12px;
  font-weight: 600;
  color: #979797;
  margin-bottom: -4px;
}

.getotp {
  display: flex;
  gap: 10px;
}

.getotp input {
  width: 60%;
}

.button-getotp {
  width: 40%;
  padding: 12px;
  border-radius: 8px;
  border: none;
  font-size: 16px;
  background: #f2f1f9;
  color: white;
}

.button-confirm {
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
