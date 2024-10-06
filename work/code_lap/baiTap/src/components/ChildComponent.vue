<template>
    <div class="modal">
        <h3>Edit Task</h3>
        <input v-model="task.name" />
        <button @click="save">Save</button>
        <button @click="$emit('closeModal')">Cancel</button>
    </div>
</template>

<script>
export default {
    props: ['task'],
    methods: {
        save() {
            this.$emit('updateTask', this.task);
        }
    }
};
</script>

<style>
.modal {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: white;
    padding: 20px;
    border: 1px solid black;
}
</style>