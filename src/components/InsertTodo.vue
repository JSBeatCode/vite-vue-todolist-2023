<template>
    <div>
        <div>
            <input 
                @change="funcOnChange"
                @keyup.enter="funcChange"
                v-model="state.todo"
                type="text"
            />
            <input
                @click="funcChange"
                type="button"
                value="Submit"
            />
        </div>
    </div>
</template>

<script>
import { reactive, toRefs } from 'vue'

export default {
    setup (props, {emit}) {
        const state = reactive({
            todo: '',
        })

        const funcOnChange = (e) => {
            const val = e.target.value;
            state.todo = val;
        }
   
        const funcChange = (e) => {
            const val = state.todo;
            emit('funcSubmit', val);
            if (e.keyCode === 13) {
                state.todo = '';
            }
        }
        return {
            state,
            funcOnChange,
            funcChange,
        }
    }
}
</script>

<style lang="scss" scoped>

</style>