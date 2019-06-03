<template>



    <input type="text" :value="value" @change="$emit('input', $event.target.value)"/>

</template>

<script>
  export default {
    name: "InputComponent",
    props: {
      value: {
        type: String,
      }
    }
  }
</script>

<style scoped>

</style>