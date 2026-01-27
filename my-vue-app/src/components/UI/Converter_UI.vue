<script setup lang="ts">
import Button_UI from './Button_UI.vue';
import Input_UI from './Input_UI.vue';

import { ref, watch } from 'vue';

const props = defineProps <{
    wallet: string;
    input: string;
    disabled: boolean;
}>()



const emits = defineEmits <{
    (e: 'update:wallet', value: string):void,
    (e: 'update:input', value: string): void
}>()

function updateWallet(value: string) {
    emits('update:wallet', value)
}

const localInput = ref(props.input)

watch(() => props.input, (val) => {
  localInput.value = val
})

watch(localInput, (val) => {
  emits('update:input', val)
})


</script>

<template>
  
    <div>

        <div>
            <Button_UI text="rub" :wallet="wallet" @select="updateWallet"/>
            <Button_UI text="usd" :wallet="wallet" @select="updateWallet"/>
            <Button_UI text="eur" :wallet="wallet" @select="updateWallet"/>
            <Button_UI text="kzt" :wallet="wallet" @select="updateWallet"/>
        </div>

        <div>
            <Input_UI v-model="localInput" :disabled="disabled"/>
        </div>

    </div>


</template>

<style scoped>

</style>
