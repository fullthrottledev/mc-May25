<template>
    <div id="app">
        <router-view/>


        <!--

        <DocumentationTable :rows="rows">
            <div :class="['asd']" slot="method">Code</div>

            <tr>
                <td>1</td>
                <td>2</td>
            </tr>
        </DocumentationTable>

        <DocumentationTable :rows="rows1"/>

        <InputComponent v-model="outerValue" />

        <InputComponent :value="outerValue" />


        <hr>
        <hr>
        <hr>
        <hr>
        <table class="table">
            <TableLine :row="{code: 'some', description: null}">
                <a href="https://google.com">Google</a>
                <Test></Test>
            </TableLine>
        </table>

        <h1>Outter</h1>

        <NewComponent/>
        -->

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
