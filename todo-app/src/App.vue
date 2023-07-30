<template>
  <div class="content">
    <form @submit.prevent="addTodo">
        <div class="field">
            <label class="label">ToDo App</label>
            <div class="control">
                <input v-model="todo" class="input" type="text" placeholder="Please enter todo..">
            </div>
        </div>
        <!-- Add button -->
        <button type="submit" class="button is-warning">Add todo</button>
    </form>
    <div v-for="a in todos"  :key="todo.id" class="card m-5">
        <div class="card-content">
            <div class="media">
                <div class="media-content">
                    <p @click="done(a)" :class="{done : a.done}" class="title is-4">{{ a.text }}</p>
                    <p class="subtitle is-6">Done: {{ a.done }}</p>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<script>
import { ref } from 'vue'
export default {
    setup() {
        const todo = ref("")
        const todos = ref([])

        const addTodo = () => {
            todos.value.push({
                done: false,
                text: todo.value,
                id:Date.now(),
            })
            todo.value = ""
        }
        const done = (todo) =>{
            todo.done = !todo.done
        }
        return {
            todo,
            todos,
            addTodo,
            done
        }
    }
}
</script>

<style lang="scss">
.done{
    text-decoration: line-through
}
</style>
