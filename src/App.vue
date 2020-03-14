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

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Quicksand&display=swap");
* {
  font-family: "Quicksand", sans-serif;
}
</style>
