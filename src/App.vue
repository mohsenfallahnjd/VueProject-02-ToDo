<template>
  <v-app>
    <v-content class="d-flex align-center">
      <TaskCard />
    </v-content>
  </v-app>
</template>

<script>
import TaskCard from "@/components/TaskCard";

export default {
  name: "App",
  components: {
    TaskCard
  }
};
</script>

// <style lang="scss">
// * {
//   font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif
// }
// </style>
