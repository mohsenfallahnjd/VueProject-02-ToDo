<template>
  <v-content>
    <v-input class="pt-10">
      <v-text-field
        type="text"
        label="Add a task"
        outlined
        v-model="inputValue"
        append-outer-icon="mdi-plus-circle"
        @click:append-outer="addingTask"
      ></v-text-field>
    </v-input>
  </v-content>
</template>

<script>
export default {
  name: "TaskInput",
  data: () => {
    return {
      inputValue: ""
    };
  },
  methods: {
    addingTask() {
      if (this.inputValue != "") {
        this.$emit("addingTask", this.inputValue);
        this.inputValue = "";
      }
    }
  }
};
</script>

<style></style>
