<script setup lang="ts">

const props = defineProps<{
    modelValue: string
    disabled: boolean
}>()

const emits = defineEmits<{
    (e: 'update:modelValue', value: string): void
}>()

function onInput(event: Event) {
    const target = event.target as HTMLInputElement
    emits('update:modelValue', target.value)
}

</script>

<template>

  <input 
    class="Input" 
    :value="modelValue"
    @input="onInput"
    :disabled="disabled"
  >

</template>

<style scoped>
.Input{
    width: 200px;
    height: 50px;
    padding: 15px;
    font-size: 25px;
}
</style>
