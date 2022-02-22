<template>
  <!-- dynamic class using task prop reminder property -->
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <h3>
      {{ task.text }}
      <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>
<script>
export default {
  name: "Enter Name",
  props: {
    task: Object,
  },
  methods: {
    // Might not need to pass the id, because it is not even passed into the next parent?? Review more
    onDelete(id) {
      this.$emit("delete-task", id);
    },
  },
};
</script>
<style scoped>
.fas {
  color: red;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid green;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
