<template>
    <section class="list">
        <ul>
            <li v-for="(task, index) in tasks" :key="index" class="task-item">
                <span>{{ task }}</span>
                <button @click="removeTask(index)"> x </button>
            </li>
        </ul>
    </section>
</template>

<script>
import ButtonsElement from './ButtonsElement.vue';

export default {
    setup(){
        const removeTask = (index) => {
            ButtonsElement.tasks.value.splice(index); 
        };
        return {removeTask};
    }
}
</script>

<style>
.list {
    padding: 2rem;
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