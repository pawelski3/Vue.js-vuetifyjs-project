<template>
  <v-list-item>
    <v-list-item-action>
      <v-btn>
        <v-icon color="pink">edit</v-icon>
      </v-btn>
    </v-list-item-action>
<v-list-item-content>
    <v-list-item-title>{{task.title}}</v-list-item-title>
    <v-list-item-subtitle>{{ task.sub_title }}</v-list-item-subtitle>
</v-list-item-content>
<v-list-item-action-text>
    <v-icon color="green">check_circle</v-icon>
</v-list-item-action-text>



  </v-list-item>
</template>
<script>
export default {
  name: "task",
  props:{
      task:Object
  }
};
</script>
