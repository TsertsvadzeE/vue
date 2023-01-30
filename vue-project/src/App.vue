<script>
import ToDolist from './toDoList.vue';
import ToDoItemForm from './ToDoItemForm.vue';
export default {
  components: {
    ToDolist,
    ToDoItemForm,
  },
  data() {
    return {
      todos: [
        {id: 1, name: "todo item 1", done: false},
        {id: 2, name: "todo item 2", done: false},
        {id: 3, name: "todo item 3", done: false}
      ],
      searchItem: null
    }
  },
  methods: {
    putNewItemIntoTodoList(data){
      this.todos.push({
        id: this.nextId,
        name: data,
        done: false
      })
    },
    changeStatus(record){
      let v = this.todos.find(item => item.id === record.id)
      v.done = !v.done
    },
    deleteItemFromTodoList(record){
      let v = this.todos.find(item => item.id === record.id)
      this.todos.splice(this.todos.indexOf(v), 1)
    }
  },
  computed: {
    nextId(){
      return this.todos.length + 1
    },
    activeTodos(){
      return this.todos.filter(value => value.done === false)
    },
    doneTodos(){
      return this.todos.filter(value => value.done ===true)
    },
  },
}
</script>
<template>
  <div class="conatainer">
    <div class="todos">
      <ToDoItemForm @onSubmitCustom="putNewItemIntoTodoList($event)"/>

      <h2>All Todo Items</h2>
      <ToDolist :data="todos" />

      <h2>Active Todos</h2>
      <ToDolist :changeStatus="true" :data="activeTodos" @changeDoneStatus="changeStatus($event)"/>

      <h2>Todos with Done Status</h2>
      <ToDolist :canDelete="true" :data="doneTodos" @onDelete="deleteItemFromTodoList($event)"/>
    </div>
    <div class="filter">
      <h2>Search</h2>
      <input type="text" v-model="searchItem"/>
      <ToDolist :data="todos.filter(value => value.name.includes(searchItem))"/>
    </div>
  </div>
</template>
<style scoped>
  .conatainer {
    display: flex;
    justify-content: space-around;
  }
</style>