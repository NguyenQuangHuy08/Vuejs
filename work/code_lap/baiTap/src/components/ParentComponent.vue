<template>
    <div>
        <ul>
            <li v-for="task in tasks" :key="task.id">
                <span :style="{ textDecoration: task.completed ? 'line-through' : 'none' }">
                    {{ task.name }}
                </span>
                <button @click="$emit('toggleTask', task.id)">Toggle Complete</button>
                <button @click="$emit('deleteTask', task.id)">Delete</button>
                <button @click="openEditModal(task)">Edit</button>
            </li>
        </ul>
        <ChildComponent v-if="showModal" :task="currentTask" @closeModal="closeModal" @updateTask="updateTask" />
    </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';

export default {
    components: { ChildComponent },
    props: ['tasks'],
    data() {
        return {
            showModal: false,
            currentTask: null
        };
    },
    methods: {
        openEditModal(task) {
            this.currentTask = { ...task };
            this.showModal = true;
        },
        closeModal() {
            this.showModal = false;
        },
        updateTask(updatedTask) {
            this.$emit('updateTask', updatedTask);
            this.showModal = false;
        }
    }
};
</script>