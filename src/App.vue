<template>
    <div id="app">
        <router-view/>
    </div>
</template>

<script>

  import NewComponent from "@/NewComponent";
  import DocumentationTable from "@/components/DocumentationTable";
  import InputComponent from "@/components/InputComponent";
  import TableLine from "@/components/TableLine";
  import Test from "@/components/Test";

  export default {
    name: 'App',
    components: {Test, TableLine, InputComponent, DocumentationTable, NewComponent},
    data() {
      return {
        outerValue: 'qwerty',
        rows: [
          {code: 'code', description: 'description'},
          {code: '$().ajax()', description: 'description'},
        ],
        rows1: [
          {code: "$('h1').remove()", description: 'description'},
          {code: 'code', description: 'description'},
        ]
      };
    },
  }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
