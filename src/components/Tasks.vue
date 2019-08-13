<template>

  <v-card style="max-height:95vh;overflow:hidden;">
    
    <v-toolbar color="blue" dark>
      <v-toolbar-title>Tilte of the list</v-toolbar-title>

      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>search</v-icon>
      </v-btn>
    </v-toolbar>
    <v-list two-line style="max-height:75vh;overflow-y:scroll;">
      <template v-for="(task,key,index) in tasks">
        <Task v-bind:key="key" :task="task" :index="key" />
      </template>
    </v-list>

    <v-divider ></v-divider>

    <v-card-actions >
      <v-layout >
        <v-flex>
          <NewTask />
        </v-flex>
      </v-layout>
    </v-card-actions>
  </v-card>
</template>

<script>
import Task from "./Task";
import NewTask from "./NewTask";
export default {
  name: "tasks",
  components: { Task, NewTask },
  data: () => ({
    tasks: [
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes",
        isComplete: false
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes",
        isComplete: true
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes",
        isComplete: true
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes",
        isComplete: true
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes",
        isComplete: true
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes",
        isComplete: true
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes",
        isComplete: true
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes",
        isComplete: true
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes",
        isComplete: true
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes",
        isComplete: true
      },
      {
        id: 1,
        title: "task title",
        sub_title: "This task contains 8 notes",
        isComplete: false
      }
    ]
  })
};
</script>
