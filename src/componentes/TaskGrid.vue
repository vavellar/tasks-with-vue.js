<template>
    <div class="task-grid">
        <template v-if="tasks.length">
            <Task v-for="(task, i) in tasks" :key="task.name" :task="task"
             @taskDeleted="$emit('taskDeleted', i)"
             @changeStateClass="$emit('changeStateClass', i)">  
            </Task>
        </template>
        <p class="no-task" v-else>Parece que sua vida está em dia :)</p>
    </div>
</template>

<script>
import Task from './Task.vue'
export default {
    props: {
        tasks: {type: Array, required: true}
    },
    components: { Task },
    
}
</script>

<style>
    .task-grid {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        flex-direction: row;
        
    }
    .no-task {
        color: #AAAAAA;
        font-size: 28px
    }


</style>