<template>
  <div id="task-card" align="center">
    <v-card max-width="450">
      <v-toolbar color="green" dark height="100em">
        <v-toolbar-title>ToDoList</v-toolbar-title>

        <v-spacer></v-spacer>
        <v-input class="pt-10">
          <v-text-field
            type="text"
            label="Add a task"
            outlined
            v-model="tasks.title"
            append-outer-icon="mdi-plus-circle"
            @click:append-outer="taskHandler"
          ></v-text-field>
        </v-input>
        <!-- <v-spacer></v-spacer>
        <v-btn fab type="submit" @click.prevent="addingTask" small>
          <v-icon>mdi-plus</v-icon>
        </v-btn> -->

        <v-spacer></v-spacer>
      </v-toolbar>

      <v-list title="Today" align="left">
        <template v-for="task in tasks">
          <!-- <v-divider v-else-if="item.divider" :key="item"></v-divider> -->

          <v-list-item :key="task.title" @click="task">
            <v-list-item-content>
              <v-list-item-title v-html="task.title"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </template>
      </v-list>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "TaskCard",
  methods: {
    taskHandler() {
      // const lastId =
      //   this.tasks.length > 0 ? this.tasks[this.tasks.length - 1].id : 0;
      // const id = lastId + 1;
      // const newTask = { id};

      // this.tasks = [...this.tasks, newTask];
      // console.log(this.inToTask);

      this.tasks.title = "";
      // console.log();
    }
  },
  data: () => ({
    tasks: [
      {
        title: ""
      }
      // { divider: true, inset: true },
    ]
  }),
  computed: {
    inToTask() {
      return this.tasks.title;
    }
  }
};
</script>
