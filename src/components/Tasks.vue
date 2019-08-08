<template>
  <v-card style="max-height:95vh;overflow:hidden;">
    <v-toolbar color="blue" dark >
      <v-toolbar-title>Tilte of the list</v-toolbar-title>

      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>search</v-icon>
      </v-btn>
    </v-toolbar>
    <v-list two-line >
      <template v-for="(task,key) in tasks">
        <Task v-bind:key="key" :task="task"  />
      </template>
    </v-list>
  </v-card>
</template>

<script>
import Task from "./Task";
export default {
  name: "tasks",
  components: { Task },
  data: () => ({
    tasks: [
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes"
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes"
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes"
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes"
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes"
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes"
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes"
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes"
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes"
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes"
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes"
      }
    ]
  })
};
</script>
