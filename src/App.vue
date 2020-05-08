<template>
  <div id="app">
    <div style="margin:10% 25%; width:250px">
      <ejs-autocomplete
        :dataSource="dataItem"
        :fields="dataFields"
        placeholder="select a game"
        popupWidth="250px"
        popupHeight="400px"
      ></ejs-autocomplete>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import { AutoCompletePlugin } from "@syncfusion/ej2-vue-dropdowns";
Vue.use(AutoCompletePlugin);

export default Vue.extend({
  name: "App",
  data() {
    return {
      dataItem: [
        { id: "Game1", Game: "Football" },
        { id: "Game2", Game: "Cricket" },
        { id: "Game3", Game: "Volleyball" },
        { id: "Game4", Game: "Baseball" },
        { id: "Game5", Game: "Ludu" }
      ],
      dataFields: { value: "Game" }
    };
  }
});
</script>

<style>
@import url(https://cdn.syncfusion.com/ej2/material.css);
</style>