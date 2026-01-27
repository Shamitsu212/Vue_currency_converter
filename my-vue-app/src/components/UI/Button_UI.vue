<script setup lang="ts">

const props = defineProps <{
    wallet: string;
    text: string;
}>()

const emits = defineEmits <{
    (e: 'select', value: string):void
}>()

function handleClick() {
    emits('select', props.text)
}

</script>

<template>
  
    <button 
        class="Button" 
        @click="handleClick"
        :disabled="text == wallet"
    >
        {{ text }}
    </button>

</template>

<style scoped>
.Button{
    width: 30px;
    height: 25px;

    background-color: rgb(0, 128, 0);
    color: white;

    border-radius: 10px 10px 0 0;
    border: none;

    transition: all ease 0.3s;
}
.Button:disabled{
    background-color: rgba(0, 128, 0, 0.4);
}
.Button:hover{
    background-color: rgb(4, 167, 4);
}
</style>
