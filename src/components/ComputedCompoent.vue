<script setup>
import {
  ref, 
  computed,
  reactive,
  watch
}from 'vue'
import Header from './components/Header.vue'
import ComponentWatch from './components/ComponentWatch.vue';


const todos = reactive([
          {
            "userId": 1,
            "id": 1,
            "title": "delectus aut autem",
            "completed": false
          },
          {
            "userId": 1,
            "id": 2,
            "title": "quis ut nam facilis et officia qui",
            "completed": false
          },
          {
            "userId": 1,
            "id": 3,
            "title": "fugiat veniam minus",
            "completed": false
          },
          {
            "userId": 1,
            "id": 4,
            "title": "et porro tempora",
            "completed": true
          }
])
const name = ref('')
const WatchName = watch(name,(newValue, oldValue)=>{
  return console.log(newValue, oldValue)
})
console.log(WatchName)

const incompleteTodos = computed(
    () => {
     return todos.filter(todo=> !todo.completed)
    }
  )
  const completeTodos = computed(
    () => {
     return todos.filter(todo=> todo.completed)
    }
  )
</script>

<template>
    <div>
    {{ name }}
    <input type="text" v-model="name">
    <ul>
        <h1>Incomplete odos</h1>
        <li v-for="todo in incompleteTodos">
        {{ todo.title }}<input type="checkbox" v-model="todo.completed">
        </li>
        </ul>
        
        <ul>
        <h1>Complete Todos</h1>
        <li v-for="todo in completeTodos">
            {{ todo.title }}
        </li>
        </ul>
  
    </div>
</template>