<template>
    <table class="table table-bordered">
        <thead>
        <tr>
            <th><slot name="method">Method</slot></th>
            <th><slot name="description">Description</slot></th>
        </tr>
        </thead>
        <tbody>


        <TableLine v-for="(row, i) in rows" :row="row"/>

        </tbody>
    </table>
</template>

<script>
  import TableLine from "@/components/TableLine";

  export default {
    name: "DocumentationTable",
    components: {TableLine},
    props: {
      rows: {
        type: [Array],
        required: true,
      }
    }
  }
</script>

<style scoped>

    td {
        text-align: left;
    }

</style>