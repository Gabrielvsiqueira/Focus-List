<template>
  <h1 class="headerPage">To-Do List</h1>
  <InputTask></InputTask>
  <ButtonsElement></ButtonsElement>
  <NewList></NewList>
</template>

<script>
import InputTask from './components/InputTask.vue';
import ButtonsElement from './components/ButtonsElement.vue';
import NewList from './components/NewList.vue';

export default {
  name: 'App',
  components: {
    InputTask,
    ButtonsElement,
    NewList
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
