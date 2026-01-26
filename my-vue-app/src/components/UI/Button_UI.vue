<script setup lang="ts">

</script>

<template>
  
    <button class="Button">

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
