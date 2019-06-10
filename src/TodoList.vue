<template>
  <div>
    <div>
      <input type="text" v-model="inputValue">
      <button @click="handleSubmit">submit</button>
    </div>

    <ul>
      <todo-item
        v-for="(item, index) in lists"
        :key="index"
        :content="item"
        :index="index"
        @delete="handleDelete">
      </todo-item>
    </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem'
export default {
  name: 'TodoList',
  components: {
    'todo-item': TodoItem
  },
  data () {
    return {
      inputValue: '',
      lists: []
    }
  },
  methods: {
    handleSubmit () {
      this.lists.push(this.inputValue)
      this.inputValue = ''
    },
    handleDelete (index) {
      this.lists.splice(index, 1)
    }
  }

}
</script>

<style>

</style>
