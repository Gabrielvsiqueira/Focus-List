<template>
  <h1 class="headerPage">To-Do List</h1>
  <InputTask :addTask="addTask"></InputTask>
  <NewList :tasks="tasks" :removeTask="removeTask"></NewList>
</template>

<script>
import { ref } from 'vue';
import InputTask from './components/InputTask.vue';
import NewList from './components/NewList.vue';

export default {
  name: 'App',
  components: {
      InputTask,
      NewList
  },
  setup() {
      const tasks = ref([]);

      const addTask = (task) => {
          tasks.value.push(task); 
      };

      const removeTask = (index) => {
          tasks.value.splice(index, 1);
      };

      return { tasks, addTask, removeTask };
  }
}
</script>

<style>
*{
  margin: auto;
  background-color: #237d39;
  font-family: 'poppins';
  color: #FFFF;
  text-align: center;
}
.headerPage{
    font-size: 8rem;
    padding: 1rem;
}
</style>
