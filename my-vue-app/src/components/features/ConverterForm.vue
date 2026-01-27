<script setup lang="ts">
import { ref, watch } from 'vue';

import Converter_UI from '../UI/Converter_UI.vue';

import { rates } from '../../data';

const firstWallet = ref("rub")
const secondWallet = ref("usd")

const userInput = ref("0")
const result = ref("0")

watch([userInput, firstWallet, secondWallet], () => {

  const amount = parseFloat(userInput.value)

  if (isNaN(amount)) {
    result.value = '0'
    return
  }

  const converted = (amount / rates[firstWallet.value]!) * rates[secondWallet.value]!
  result.value = converted.toFixed(2)
})
</script>

<template>
  <form class="Form">
    <div class="Form_Container">
      <Converter_UI
        v-model:wallet="firstWallet"
        v-model:input="userInput"
        :disabled="false"
      />
    </div>

    <div class="Form_Container">
      <Converter_UI
        v-model:wallet="secondWallet"
        v-model:input="result"
        :disabled="true"
      />
    </div>
  </form>
</template>


<style scoped>
.Form{
    width: 500px;
    height: 140px;

    background-color: white;
    
    box-shadow: 0px 5px 10px 5px rgba(0, 0, 0, 0.3);

    border-radius: 16px;

    display: flex;
    flex-direction: row;
    align-items: center;


    padding: 25px 30px 20px 40px;
}
.Form_Container{
    width: 50%;
    height: 100%;
}
</style>
