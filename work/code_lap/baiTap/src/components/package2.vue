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

<template>
    <div class="controller">
        <div class="header">
            <h5>Đây là component con</h5>
        </div>

        <div class="body">
            <h6>To do list</h6>
            <div class="modal">
                <h3>Edit Task</h3>
                <input v-model="task.name" />
                <button @click="save">Save</button>
                <button @click="$emit('closeModal')">Cancel</button>
            </div>
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
