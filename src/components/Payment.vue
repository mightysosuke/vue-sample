<script setup lang="ts">
const itemName1 = 'desk'
const itemName2 = 'bike'

const price1 = 40000
const price2 = 20000

const url1 = 'https://www.amazon.co.jp/dp/B08C1LR9RC'
const url2 = 'https://www.amazon.co.jp/dp/B08F5Z3RK5'

const buy = (itemName: string) => {
  alert('Are you sure to buy ' + itemName + '?')
}

const input = (event: any) => {
  console.log('event: ', event.target.value)
}
</script>

<template>
  <div class="container">
    <h1>Payment</h1>
    <input v-on:input="input" />
    <div class="payment">
      <label>{{ itemName1 }}</label>
      <label>{{ price1 }} 円</label>
      <a v-bind:href="url1">bought at...</a>
      <button v-on:click="buy(itemName1)">BUY</button>
    </div>
    <div class="payment">
      <label>{{ itemName2 }}</label>
      <label>{{ price2 }} 円</label>
      <a v-bind:href="url2">bought at...</a>
      <button v-on:click="buy(itemName2)">BUY</button>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.payment {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 80px;
  width: 400px;
  background-color: aliceblue;
  margin-bottom: 40px;
}

label {
  font-size: 20px;
  font-weight: bold;
}
</style>