<template>
    <tr>
        <td :class="['static', i % 2 === 0 ? 'even' : 'odd']">
            <code class="highlighter-rouge">
                {{ row.code }}
            </code>
        </td>
        <td>
            {{ row.description }}
            <slot>
                Default value
            </slot>
        </td>
    </tr>
</template>
<script>
  export default {
    name: 'TableLine',
    props: {
      row: {}
    }
  }
</script>
<style scoped>

    td {
        text-align: left;
    }

</style>