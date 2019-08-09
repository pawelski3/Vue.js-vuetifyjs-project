<template>
  <v-card height="100%">
    <v-toolbar color="pink" dark>
      <v-toolbar-title>Options</v-toolbar-title>
    </v-toolbar>

    <v-list>
      <v-list-group prepend-icon="sort">
        <v-list-item slot="activator">
          <v-list-item-content>
            <v-list-item-title>Some title</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

<v-list-item>
          <v-list-item-content>
            <v-list-item-title>Some title1</v-list-item-title>
          </v-list-item-content>
        </v-list-item>


      </v-list-group>
    </v-list>
  </v-card>
</template>
<script>
export default {
  name: "optionsBar"
};
</script>
