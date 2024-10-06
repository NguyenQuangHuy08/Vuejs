<script>
import package2 from './package2.vue';

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

<template>
    <div class="controller">
        <div class="header">
            <h5>Đây là component cha</h5>
        </div>

        <div class="body">
            <h6>To do list</h6>

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

            <package2 v-if="showModal" :task="currentTask" @closeModal="closeModal" @updateTask="updateTask" />

        </div>

    </div>
</template>

<style scoped>
.controller {

    /* max-width: 1200px; */
    position: absolute;
    top: 0px;
    left: 100px;
    border: 1px solid red;
    width: 1200px;
}
</style>
