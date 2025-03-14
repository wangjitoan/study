<template>
   
    <div>
        <h1>emitTest</h1>
        <p>{{emittest}}</p>
        <button @click="click">我是加一按钮</button>
        <input :value="modelValue" @input="$emit('update:modelValue',$event.target.value)" >我是</input>
    </div>
</template>
<script setup>
import { ref,defineProps,defineEmits } from 'vue';
const props=defineProps(['emittest','modelValue','pagenum'])
const emit=defineEmits(['update:modelValue','update:pagenum'])
const emitRef=ref(1)
function click(){
    emit('update:pagenum',props.pagenum+1)
}
</script>>