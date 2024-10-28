<template>
    <section class="list">
        <h3 id="getText">Write and add the task you want to include.</h3>
        <input class="getTask" v-model="newTask" type="text" placeholder="Write your task..">
        <button id="addTask" @click="addTask()">Add Task</button>
        
        <ul>
            <li v-for="(task, index) in tasks" :key="index" class="task-item">
                <span>{{ task }}</span>
                <button @click="removeTask(index)"> x </button>
            </li>
        </ul>
    </section>
</template>

<script>
import { ref } from 'vue';

export default {
    setup() {
        const newTask = ref(''); 
        const tasks = ref([]); 

        const addTask = () => {
            if (newTask.value !== '') {
                tasks.value.push(newTask.value);
                newTask.value = ''; 
            }
        };

        const removeTask = (index) => {
            tasks.value.splice(index); 
        };

return {newTask, tasks, addTask,removeTask };
    }
}
</script>

<style>
.list {
    padding: 2rem;
}
#getText {
    font-size: 1.5rem;
    margin: 12px;
}
.getTask {
    margin: 1rem;
    border: 2px solid #FFFF; 
    color: #FFFF;
    width: 20rem;
    height: 2.5rem;
    background-color: #5a5959; 
}
.getTask::placeholder {
    color: #bebcbc;
}
#addTask {
    font-size: 1.5ch;
    border: 2px solid #FFFF;
    background-color: #555;
    color: #FFF; 
    cursor: pointer;
    height: 2rem;
}
ul {
    list-style-type: none; 
    padding: 0;
    width: 75rem;
}
.task-item {
    border: 1px solid #FFFF;
    padding: 1rem;
    margin: 5px 0; 
    display: flex;
    justify-content: space-between; 
    align-items: center; 
}
.task-item button {
    background-color: #E74C3C; 
    color: #FFFF;
    border: none;
    padding: 5px 10px;
    cursor: pointer;
}
</style>
