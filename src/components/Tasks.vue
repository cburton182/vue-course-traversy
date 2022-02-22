<template>
  <!-- dynamically tenders Task component based on array data coming in from prop "tasks" -->
  <!-- iterables must have a :key -->
  <!-- summary: task array comes in as prop, looped over and each array item creates a new Task component-->
  <div v-for="task in tasks" :key="task.id">
    <Task
      @toggle-reminder="$emit('toggle-reminder', task.id)"
      @delete-task="$emit('delete-task', task.id)"
      :task="task"
    />
  </div>
</template>

<script>
import Task from "./Task";
export default {
  name: "Tasks",
  props: {
    // will be receiving value from parent
    tasks: Array,
  },
  components: {
    Task,
  },
  emits: ["delete-task", "toggle-reminder"],
  // emits: ["randomname"],
  // Proof that event is not propogating up, but a new event is being emitted.

  //   emits array needed when propogating up?
};
</script>
