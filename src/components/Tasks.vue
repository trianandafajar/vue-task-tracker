<template>
  <div :key="task.id" v-for="task in tasks">
    <Task
      @delete-task="$emit('delete-task', task.id)"
      @toggle-reminder="$emit('toggle-reminder', task.id)"
      :task="task"
    />
  </div>
</template>

<script>
import Task from "./Task.vue";
export default {
  name: "Tasks",
  props: {
    tasks: Array,
  },
  components: { Task },
  emits: ["delete-task", "toggle-reminder"],
};
</script>

<style></style>
