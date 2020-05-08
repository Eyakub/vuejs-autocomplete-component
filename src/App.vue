<template>
  <div id="app">
    <div style="margin:10% 25%; width:250px">
      <ejs-autocomplete
        :dataSource="dataItem"
        :fields="dataFields"
        :query="dataQuery"
        :highlight="true"
        placeholder="Search for employee"
        popupWidth="250px"
        popupHeight="400px"
      ></ejs-autocomplete>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import { AutoCompletePlugin } from "@syncfusion/ej2-vue-dropdowns";
import { DataManager, WebApiAdaptor, Query } from '@syncfusion/ej2-data';
Vue.use(AutoCompletePlugin);

export default Vue.extend({
  name: "App",
  data() {
    return {
      // dataItem: [
      //   { id: "Game1", Game: "Football" },
      //   { id: "Game2", Game: "Cricket" },
      //   { id: "Game3", Game: "Volleyball" },
      //   { id: "Game4", Game: "Baseball" },
      //   { id: "Game5", Game: "Ludu" }
      // ],
      dataItem: new DataManager({
        url: 'https://ej2services.syncfusion.com/production/web-services/api/Employees',
        adaptor: new WebApiAdaptor,
        crossDomain: true
      }),
      dataFields: { value: "FirstName" },
      dataQuery: new Query().select(['FirstName', 'EmployeeID']).take(9).requiresCount(),
    };
  }
});
</script>

<style>
@import url(https://cdn.syncfusion.com/ej2/material.css);
</style>