<template>
    <div>
        <div v-for="todo in todoList" v-bind:key="todo.id">
            <div @click="$emit('funcDel', todo.id)">
                {{ todo.content }}
            </div>
        </div>
    </div>
</template>

<script>
// import { reactive, toRefs } from 'vue'

export default {
    name: 'ListTodo',
    props: {
        todoList: Array
    },
    emit: ['funcDel']
}
</script>

<style lang="scss" scoped>

</style>