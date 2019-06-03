<template>
    <div id="app">
        <h1>Hello, {{name}}</h1>
        <span v-if="items.length > 3">Many</span>
        <span v-for="item in evenItems" v-show="item % 2 === 0" :key="item">
            {{ item }}
        </span>

        <input type="text" v-bind:value="name" v-on:change="name = $event.target.value"/>

        <input type="text" v-model.lazy="name"/>

        <input type="text" v-model="nameReversed"/>

        <input type="text" v-model="foo.a"/>
        <input type="text" v-model="foo.b"/>
        <input type="text" v-model="foo.c"/>

<!--        <textarea id="ta1">Initial</textarea>-->
    </div>
</template>

<script>
  export default {
    name: "Test",
    data() {
      return {
        name: 'vue',
        items: [1, 2, 3, 4],
        foo: {
          a: 1,
          b: 2,
        }
      };
    },
    watch: {
      name(value) {
        console.log(`Name changed: ${value}`);
      },
      'foo.a': {
        deep: true,
        handler: function(newVal, oldVal) {
          console.log("Foo changed", this.foo);
        },
      },
    },
    computed: {
      evenItems: function() {
        return this.items.filter(item => item % 2 === 0);
      },
      nameReversed: {
        set: function() {
          console.log(console.log("Trying to set computed"));
        },
        get: function() {
          return this.name.split('').reverse().join('');
        }
      },
      reversedNested() {
        return this.nameReversed();
      }
    },
    mounted() {
      this.$set(this.foo, 'c', 3);
    },
    methods: {
      update() {
        this.$forceUpdate();
      }
    }
  }
</script>

<style>

    h1 {
        color: green;
    }
</style>