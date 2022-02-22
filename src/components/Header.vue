<template>
  <header>
    <!-- title is a prop that will be defined where this compenent is exported: in this case App.vue -->
    <h1>{{ title }}</h1>
    <!-- text and color are props that were declared in button component and are now being defined.  Now this button can be used elsewhere with different text and color -->
    <!-- Need Button here -->
    <Button
      v-show="homePage"
      @btn-click="$emit('toggle-add-task')"
      :text="showAddTask ? 'Close' : 'Add Task'"
      :color="!showAddTask ? 'Green' : 'Red'"
    />
  </header>
</template>

<script>
import Button from "./Button";
export default {
  name: "Name",
  props: {
    title: {
      type: String,
    },
    showAddTask: Boolean,
  },
  components: {
    Button,
  },
  computed: {
    homePage() {
      if (this.$route.path === "/") {
        return true;
      } else return false;
    },
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
