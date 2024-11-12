<template>
    <h3 id="getText">Write and add the task you want to include.</h3>
    <input class="getTask" v-model="newTask" type="text" placeholder="Write your task.." />
    <button id="addTask" @click="addTaskToList">Add Task</button> 
</template>

<script>
import { ref } from 'vue';

export default {
    props: {
        addTask: {
            type: Function,
            required: true
        }
    },
    setup(props) {
        const newTask = ref('');

        const addTaskToList = () => {
            if (newTask.value.trim() !== '') {
                props.addTask(newTask.value);
                newTask.value = ''; 
            }
        };
        return { newTask, addTaskToList };
    }
}
</script>

<style>
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
    font-size: 1.5rem;
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
</style>