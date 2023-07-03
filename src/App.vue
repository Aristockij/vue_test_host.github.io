<template>
  <div class="app">
    <div class="wrap">
      <h1>Список:</h1>
      <items-list :info="info" @item-selected="handleItemSelected"/>
      <val-popup  v-model:show="dialogVisible">
        <item-form :selectedItem="selectedItem" @update:show-dialog="dialogVisible = $event"/>
      </val-popup>
    </div>


  </div>
</template>

<script>

import ItemsList from "./components/ItemsList.vue";
import ItemForm from "./components/ItemForm.vue";


export default {
  name: "App",
  components: {ItemsList, ItemForm},
  data(){
    return {
      info:[
       {
         id: 1,
         name: "foo1",
         value: "bar1",
       },
       {
         id: 2,
         name: "foo2",
         value: "bar2",
       },
       {
         id: 3,
         name: "foo3",
         value: "bar3",
       },
       {
         id: 4,
         name: "foo4",
         value: "bar4",
       },
        {
          id: 5,
          name: "foo5",
          value: "bar5",
        },
        {
          id: 6,
          name: "foo6",
          value: "bar6",
        },
        {
          id: 7,
          name: "foo7",
          value: "bar7",
        },
        {
          id: 8,
          name: "foo8",
          value: "bar8",
        },
        {
          id: 9,
          name: "foo8",
          value: "bar8",
        },
        {
          id: 10,
          name: "foo10",
          value: "bar10",
        },
        {
          id: 11,
          name: "foo11",
          value: "bar11",
        },
        {
          id: 12,
          name: "foo12",
          value: "bar12",
        },
        {
          id: 13,
          name: "foo13",
          value: "bar13",
        },
        {
          id: 14,
          name: "foo14",
          value: "bar14",
        },
        {
          id: 15,
          name: "foo15",
          value: "bar15",
        },
        {
          id: 16,
          name: "foo16",
          value: "bar16",
        },
        {
          id: 17,
          name: "foo17",
          value: "bar17",
        },
        {
          id: 18,
          name: "foo18",
          value: "bar18",
        },
        {
          id: 19,
          name: "foo18",
          value: "bar18",
        },
        {
          id: 20,
          name: "foo20",
          value: "bar20",
        },
      ],
      selectedItem: null,
      dialogVisible: false,
    }
  },
  emits: ['item-selected'],
  methods: {
    handleItemSelected(item) {
      this.selectedItem = item;
      this.dialogVisible = true;
    },
  },
}
</script>

<style scoped>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.app{
  padding: 50px;
}
.wrap{
  max-width: 600px;
  margin: 0 auto;
}

</style>