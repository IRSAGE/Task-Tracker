<template>
    <div v-for="task in tasks" :key="task.id">
        <Task @delete-task="$emit('delete-task', task.id)" @toggle-reminder="$emit('toggle-reminder', task.id)"
            :task="task"></Task>
    </div>
</template>

<script>
import Task from "./Task";
export default {
    name: "Tasks",
    props: {
        tasks: Array,
    },
    components: {
        Task,
    },
    emits: ["delete-task", "toggle-reminder"],
};
</script>
