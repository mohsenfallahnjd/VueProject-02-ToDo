<template>
  <div id="task-card" align="center">
    <v-card max-width="450">
      <v-toolbar color="green" dark height="100em">
        <v-toolbar-title>ToDoList</v-toolbar-title>
        <v-spacer></v-spacer>
        <TaskInput @addingTask="addingTask" />
      </v-toolbar>

      <v-list title="Today" align="left" min-height="300px">
        <div v-for="task in tasks" :key="task.id">
          <v-divider v-if="task.divider"></v-divider>
          <v-list-item class="listItem" :key="task.id">
            <v-list-item-content class="listItem__content">
              <div class="listItem__content__item font-weight-bold">
                <v-list-item-title
                  v-if="task.done"
                  class="decoration"
                  v-html="task.title"
                ></v-list-item-title>
                <v-list-item-title
                  v-else
                  v-html="task.title"
                ></v-list-item-title>
                <v-icon
                  medium
                  v-if="task.done"
                  color="green "
                  class="doneBtn"
                  @click="doneItem(task.id)"
                >
                  mdi-check
                </v-icon>
                <v-icon
                  medium
                  class="doneBtn"
                  v-else
                  @click="doneItem(task.id)"
                >
                  mdi-check
                </v-icon>
                <v-icon class="removeBtn" medium @click="removeItem(task.id)">
                  mdi-close
                </v-icon>
              </div>
            </v-list-item-content>
          </v-list-item>
        </div>
      </v-list>
    </v-card>
  </div>
</template>

<script>
import TaskInput from "./TaskInput";
export default {
  name: "TaskCard",
  components: {
    TaskInput
  },
  data: () => ({
    tasks: []
  }),
  methods: {
    addingTask(inputValue) {
      const newTodo = {
        id:
          this.tasks.length > 0 ? this.tasks[this.tasks.length - 1].id + 1 : 0,
        title: inputValue,
        divider: this.tasks.length > 0 ? true : false,
        done: false
      };

      this.tasks.push(newTodo);
    },
    doneItem(id) {
      this.tasks.forEach(task => {
        if (task.id == id) {
          task.done = !task.done;
        }
      });
    },
    removeItem(id) {
      this.tasks = this.tasks.filter(task => task.id != id);
    }
  }
};
</script>

<style lang="scss" scoped>
.listItem {
  padding: 8px;
  &__content {
    border-radius: 5px;
    &:hover {
      box-shadow: 0px 0px 4px 0px rgba(0, 0, 0, 0.25);
    }

    &__item {
      display: flex;
      justify-content: space-between;
      padding: 5px 10px;
      box-sizing: border-box;

      .doneBtn {
        margin: 0px 15px;
        &:hover {
          color: rgba(76, 175, 80);
        }
      }
      .removeBtn {
        &:hover {
          color: #f44336;
        }
      }
    }
  }
}

.decoration {
  text-decoration: line-through;
  opacity: 0.5;
}

.unborder {
  border: none;
  outline: none;
}
</style>
