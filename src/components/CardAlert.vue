<script setup>
import { defineProps,computed, defineEmits } from 'vue';

defineProps({
    variant:String,
    text:String
})

//this-->(refer to component ) doesn't work in arrow functions
computed(function baseClass(){
    return ['alert', this.variant]
})

const emit = defineEmits('Clicked')
function onClick(){
    emit('close')
    console.log('clicou aqui')
}
</script>
<template>
    <div :class="`alert ${variant}`">
        Seu pedido foi enviado com sucesso!{{ variant }}
        <slot/>
        <button @click="onClick()">X</button>
    </div>
</template>


<style scoped>

.alert{
    display: flex;
    justify-content: space-between;
    padding: 5px;
    background-color: #ddd;

}
.sucess{
    background-color: rgb(5, 153, 42);
}


.danger{
    background-color: rgb(180, 17, 17);
}

</style>