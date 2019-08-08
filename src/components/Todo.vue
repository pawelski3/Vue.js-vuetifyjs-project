<template>
  <div>
    <v-container fill-height>
      <v-layout row align-space-between justify-space-between>
        <v-flex lg3 pr-2>
          <Lists />
        </v-flex>

        <v-flex lg6 pr-2 pl-2>Tasks</v-flex>

        <v-flex lg3 pl-2>Options</v-flex>
      </v-layout>
    </v-container>
    <v-footer height="auto" color="indigo">
      <v-layout justify-center>
        <v-flex indigo white--text text-xs-center>
          &copy;2019
          <strong>pawelgawel.c0.pl</strong>
        </v-flex>
      </v-layout>
    </v-footer>
  </div>
</template>



<script>
import Lists from "./Lists";
export default {
  name: "todo",
  components: { Lists }
};
</script>
