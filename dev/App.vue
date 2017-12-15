<template>
  <div>
    <vue-good-table
      :paginate="true"
      :columns="columns"
      :rows="rows"
      :selectable="true"
      :line-numbers="true"
      @selectedRows="log">
      <template slot="table-actions">
        ewer

      </template>
      <template slot="table-row-after" scope="props">
        <td><a class="button lightbox" href="#" @click="onClick" >detail</a></td>
      </template>
    </vue-good-table>
  </div>
</template>

<script>
  import Vue from 'vue';
  import VueGoodTable from '../src/index';
  Vue.use(VueGoodTable);
  export default {
    name: 'test',
    data(){
      return {
        columns: [
          {
            label: 'Name',
            field: 'name',
            type: 'text',
          },
          {
            label: 'Age',
            field: 'age',
            type: 'number',
          },
          {
            label: '',
            sortable: false,
          },
        ],
//        rows: [],
        rows: [
          { name: "John", age: "20" },
          { name: "Jane", age: "24" },
          { name: "Susan", age: "16" },
          { name: "Chris", age: "55"},
          { name: "Dan", age: "40" },
          { name: "John", age: "20" },
//          { name: "Jane", age: "24" },
//          { name: "Susan", age: "16" },
//          { name: "Chris", age: "55"},
//          { name: "Dan", age: "40" },
//          { name: "John", age: "20" },
//          { name: "Jane", age: "24" },
//          { name: "Susan", age: "16" },
//          { name: "Chris", age: "55"},
//          { name: "Dan", age: "40" }
        ],
      };
    },
    methods: {
      onClick() {
        this.rows.splice(0, 1);
        console.log('onClick', this.rows);
      },
      log(data) {
        console.log('log', this.rows, data);
      }
    }
  };
</script>

<style lang="css">
  .row-style{
    background-color: red;
  }
</style>

