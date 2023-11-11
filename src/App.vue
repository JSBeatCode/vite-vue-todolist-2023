<template>
  <HelloWorld msg="TodoList" />
  
  <InsertTodo 
    @funcSubmit="funcSubmit"
  />

  <ListTodo 
    @funcDel="funcDel"
    :todoList="state.todoList"
  />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import InsertTodo from './components/InsertTodo.vue';
import ListTodo from './components/ListTodo.vue';
import { onMounted, onUpdated, reactive, toRefs } from 'vue';
import { v4 as uuidv4 } from 'uuid';

export default {
  name: 'App',
  components: {
    HelloWorld,
    InsertTodo,
    ListTodo,
  },
  setup () {
    const state = reactive({
      todoList: []
    });

    onMounted(() => {

    })

    onUpdated(() => {

    })

    const funcSubmit = (val) => {
      state.todoList = [
        ...state.todoList,
        {id: uuidv4(), content: val}
      ]
    }

    const funcDel = (id) => {
      state.todoList = state.todoList.filter(todo => todo.id !== id)
    }

    return {
      state,
      onMounted,
      onUpdated,
      funcSubmit,
      funcDel
    }
  }
}
</script>


<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
