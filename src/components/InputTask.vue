<template>
    <h3 id="getText">Write and add the task you want to include.</h3>
    <input class="getTask" v-model="newTask" type="text" placeholder="Write your task..">
</template>

<script>
import { ref } from 'vue';
import ButtonsElement from './ButtonsElement.vue';

export default {
    setup(){
        const newTask = ref(''); 
        const tasks = ref([]); 

        return {newTask, tasks, ButtonsElement};
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
</style>