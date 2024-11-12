<template>
        <button id="addTask" @click="addTask()">Add Task</button>
</template>

<script>
import { } from "vue";
import InputTask from "./InputTask.vue";
import NewList from "./NewList.vue";

export default {
    setup(){
    const addTask = () => {
            if (InputTask.newTask.value !== '') {
                InputTask.tasks.value.push(InputTask.tasks.value);
                InputTask.newTask.value = ''; 
            }
        }
    const removeTask = (index) => {
            NewList.tasks.value.splice(index); 
        };
    return {InputTask, addTask, removeTask};
    }
}
</script>

<style>
#addTask {
    font-size: 1.5ch;
    border: 2px solid #FFFF;
    background-color: #555;
    color: #FFF; 
    cursor: pointer;
    height: 2rem;
}
</style>