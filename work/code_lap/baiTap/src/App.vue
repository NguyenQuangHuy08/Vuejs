<script>
import { reactive } from 'vue';
import ParentComponent from './components/ParentComponent.vue';

export default {
  components: { ParentComponent },
  setup() {
    const state = reactive({
      tasks: [
        {
          id: 1,
          name: 'Task 1',
          completed: false
        },
        {
          id: 2,
          name: 'Task 2',
          completed: false
        }
      ],
      newTask: ''
    });
    //Todo code add 
    const addTask = () => {
      if (state.newTask) {
        state.tasks.push({
          id: Date.now(),
          name: state.newTask,
          completed: false
        });
        state.newTask = '';
      }
    };

    const deleteTask = (taskId) => {
      state.tasks = state.tasks.filter(task => task.id !== taskId);
    };

    const toggleTask = (taskId) => {
      const task = state.tasks.find(task => task.id === taskId);
      if (task) {
        task.completed = !task.completed;
      }
    };

    return { state, addTask, deleteTask, toggleTask };
  }
};
</script>

<template>
  <div>
    <h1>To-do List</h1>
    <ParentComponent :tasks="state.tasks" @deleteTask="deleteTask" @toggleTask="toggleTask" />
    <input v-model="state.newTask" placeholder="Add a new task" />
    <button @click="addTask">Add Task</button>
  </div>
</template>
