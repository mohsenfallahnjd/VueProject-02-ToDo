<template>
  <v-app>
    <v-content class="d-flex align-center">
      <TaskCard />
    </v-content>
  </v-app>
</template>

<script>
import TaskCard from "@/components/TaskCard.vue";
export default {
  name: "App",

  components: {
    TaskCard
  },
  methods: {
    addingTask() {
      console.log();
    }
  },
  data: () => ({
    //
  })
};
</script>
