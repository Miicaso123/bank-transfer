<template>
  <div class="choose">
    <div class="choose-card">
      <select>
        <option disabled selected>Choose account / card</option>
        <option v-for="account in accounts" :key="account.id">
          Account {{ account.Account }}
        </option>
      </select>
    </div>

    <div class="choose-transaction">
      <b>Choose transaction</b>
      <div class="transaction-options">
        <div
          class="option"
          :class="{ active1: selectTransaction === 0 }"
          @click="selectTransaction = selectTransaction === 0 ? null : 0"
        >
          <img src="/images/transfer1.svg" alt="transfer" class="transfer-icon" />Transfer via card
          number
        </div>
        <div
          class="option"
          :class="{ active2: selectTransaction === 1 }"
          @click="selectTransaction = selectTransaction === 1 ? null : 1"
        >
          <img src="/images/transfer2.svg" alt="transfer" class="transfer-icon" />Transfer to the
          same bank
        </div>
        <div
          class="option"
          :class="{ active3: selectTransaction === 2 }"
          @click="selectTransaction = selectTransaction === 2 ? null : 2"
        >
          <img src="/images/transfer3.svg" alt="transfer" class="transfer-icon" />Transfer to
          another bank
        </div>
      </div>
    </div>

    <div class="choose-beneficiary">
      <div class="header">
        <b>Choose beneficiary</b>
        <p>Find beneficiary</p>
      </div>
      <div class="beneficiaries">
        <div class="add-new"><div class="plus">+</div></div>
        <div
          class="user"
          :class="{ active: selectBeneficiary === 0 }"
          @click="selectBeneficiary = selectBeneficiary === 0 ? null : 0"
        >
          <img src="/images/chooseuser1.jpg" alt="user" />
          <p>Emma</p>
        </div>
        <div
          class="user"
          :class="{ active: selectBeneficiary === 1 }"
          @click="selectBeneficiary = selectBeneficiary === 1 ? null : 1"
        >
          <img src="/images/chooseuser2.jpg" alt="user" />
          <p>Justin</p>
        </div>
      </div>
    </div>

    <FormCardNumber />
  </div>
</template>

<script setup lang="ts">
const selectTransaction = ref<number | null>(null);
const selectBeneficiary = ref<number | null>(null);

defineProps<{ accounts: { id: number; Account: number }[] }>();
</script>

<style scoped>
.choose-card select {
  width: 100%;
  padding: 12px;
  border-radius: 8px;
  border: 1px solid #ccc;
  font-size: 16px;
}

.choose-transaction {
  margin-top: 24px;
}

.choose-transaction b {
  color: #989898;
  font-size: 12px;
}

.transaction-options {
  display: flex;
  gap: 12px;
  overflow-x: auto;
  scrollbar-width: none;
  margin-top: 12px;
}

.transaction-options::-webkit-scrollbar {
  display: none;
}

.option {
  min-width: 110px;
  height: 90px;
  background-color: #e0e0e0;
  padding: 16px;
  border-radius: 12px;
  font-size: 14px;
  color: white;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.option.active1 {
  background-color: #3b28d2;
}

.option.active2 {
  background-color: #c84b4b;
}

.option.active3 {
  background-color: #ffaf2a;
}

.transfer-icon {
  width: 28px;
  height: 28px;
}

.choose-beneficiary {
  margin-top: 24px;
}

.choose-beneficiary .header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 12px;
}

.choose-beneficiary .header b {
  color: #989898;
  font-size: 12px;
}

.choose-beneficiary .header p {
  color: #3b28d2;
  font-weight: 700;
  font-size: 12px;
}

.beneficiaries {
  display: flex;
  gap: 12px;
  align-items: center;
}

.add-new {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 50%;
  height: 120px;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 1px 5px;
  border-radius: 12px;
}

.plus {
  display: flex;
  justify-content: center;
  align-items: center;
  background: #f2f1f9;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  font-size: 48px;
  color: white;
}

.user {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 8px;
  width: 50%;
  height: 120px;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 1px 5px;
  border-radius: 12px;
}

.user.active {
  background: #3b28d2;
  color: white;
}

.user img {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  object-fit: cover;
}

.user p {
  margin: 0;
  font-size: 14px;
  font-weight: 500;
}
</style>
