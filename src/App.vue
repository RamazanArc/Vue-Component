<template>
<div class="container">
  <h3 class="text-center">ToDo List</h3>
  <hr class="my-2">
  <AddSection  :addNewTodo="addNewTodo" @add-todo="addNewTodo" />
  <TodoList @delete-todo-item="deleteItem"  :myData="todoList" />
  <ResultBar :itemCount="todoList.length" />
</div>
</template>

<script>
import AddSection from "@/components/AddSection.vue";
import TodoList from "@/components/TodoList.vue";
import ResultBar from "@/components/ResultBar.vue";



export default {
  components : {
    AddSection,
    TodoList,
    ResultBar
  },

  created() {
    setTimeout(() =>{
      this.todoList= [
        {id : 1, text : "Todo #1"},
        {id : 2, text : "Todo #2"},
        {id : 3, text : "Todo #3"},
        {id : 4, text : "Todo #4"},
        {id : 5, text : "Todo #5"},
        {id : 6, text : "Todo #6"}
      ];
    }, 2000);
  },
  data(){
    return{
      todoList : []
    }
  },
  methods : {
    testEvent(data){
      alert(data);
    },

    deleteItem(todoItem){
      this.todoList = this.todoList.filter((t) => t !== todoItem);
    },
    addNewTodo(todo){
      this.todoList.push({
        id : new Date().getTime(),
        text: todo
      });

    }
  }
}
</script>

<style>


</style>
