<script setup>
import { ref } from 'vue';


const text = ref("");
const emits = defineEmits(["onNewItem"])

function handleSubmit(){
    if(text !== ""){
        //llamar emit
        emits("onNewItem",text)
        text.value = ""
    }
}

</script>

<template>
    <form @submit.prevent="handleSubmit">
        <input type="text" v-model="text">
    </form>
</template>

<style scoped>

form{
    margin-bottom: 10px;
}

input{
    width: 100%;
    box-sizing: border-box;
}

</style>