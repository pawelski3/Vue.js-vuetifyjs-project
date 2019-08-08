<template>
  <v-container fill-height>
    <v-layout row>
      <v-flex lg3>
        <Lists />
      </v-flex>
    </v-layout>
  </v-container>
</template>



<script>
import Lists from "./Lists";
export default {
  name: "todo",
  components: { Lists }
};
</script>
