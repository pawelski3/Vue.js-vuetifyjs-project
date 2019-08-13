<template>
<div>
  <v-card height="100%">
    <v-toolbar color="pink" dark>
      <v-toolbar-title>Options</v-toolbar-title>
    </v-toolbar>

    <v-list style="outline:2px solid red;">
      <v-list-group
        v-for="(item,key) in items"
        v-bind:key="key"
        v-model="items.active"
        :prepend-icon="item.action"
        no-action
        sub-group
 
      >
        <v-list-item slot="activator">
          <v-list-item-content>
            <v-list-item-title>{{item.title}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>

         <v-list-item
            v-for="(subItem, key) in item.items"
            v-bind:key="key"
            v-on="item.action === 'sort' ? { click: () => sort(subItem.by) } : { click: () => filter(subItem.by) }"
            active-class
          >
          <v-list-item-content>
            <v-list-item-title>{{ subItem.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        
      </v-list-group>


<v-list-group prepend-icon="filter" no-action>
  <v-list-item slot="activator">
    <v-list-item-content>
      <v-list-item-title>List options</v-list-item-title>
    </v-list-item-content>
  </v-list-item>

 <v-list-item >
    <v-list-item-content>
      <v-list-item-title class="danger">Remove list</v-list-item-title>
    </v-list-item-content>
  </v-list-item>

<v-list-item >
    <v-list-item-content>
      <v-list-item-title class="danger">Change background</v-list-item-title>
    </v-list-item-content>
  </v-list-item>

</v-list-group>





    </v-list>
  </v-card>
 <MoreOptions/>
</div>
</template>



<script>
import MoreOptions from './MoreOptions'
export default {
  name: "optionsBar",
  components: { MoreOptions },
  data: () => ({
    items: [
      {
        action: "sort",
        title: "Sort by",
        active: true,
        items: [
          {
            title: "Date",
            by: "date"
          },
          {
            title: "Name",
            by: "name"
          }
        ]
      },
      {
        action: "filter_list",
        title: "Filter by",
        active: false,
        items: [
          {
            title: "Remaining",
            by: "remaining"
          },
          {
            title: "Completed",
            by: "completed"
          },
          {
            title: "All",
            by: "all"
          }
        ]
      }
    ]
  }),
  methods:{
    sort(value){
      console.log("sort by"+value);
    },
    filter(value){
console.log("filter by"+value);
    }
  }
};
</script>
