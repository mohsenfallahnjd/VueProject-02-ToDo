<template>
  <v-content>
    <v-text-field
      type="text"
      value="message"
      label="Add a task"
      v-model="task.text"
    ></v-text-field>
  </v-content>
</template>

<script>
export default {
  name: "TaskInput"
};
</script>

<style></style>
