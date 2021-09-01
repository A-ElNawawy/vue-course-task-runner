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
import Task from "./task.vue";
export default {
  name: "Tasks",
  components: {
    Task,
  },
  props: {
    tasks: Object,
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>
