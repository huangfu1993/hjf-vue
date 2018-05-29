<template>
  <div>
    <p v-on:click="showtext(item)" :class="color === item.name ? 'red' : ''" v-for="item in aaa">
      {{item.name}}: {{item.age}}
      <span v-if="item.age > 16">大龄青年</span>
    </p>
  </div>
</template>

<script>
  export default {
    name: "Men",
    props: {
      name: String,
    },

    data() {
      return {
        color: name,
        aaa: [
          {name: 'xiaoming', age: 13},
          {name: 'xiaohong', age: 13},
          {name: 'xiaofang', age: 13},
          {name: 'xiaobai', age: 18},
        ]
      }
    },

    methods: {
      showtext(item) {
        this.color = item.name
      }
    },
  }
</script>

<style>
  .red {
    color: red;
  }

</style>
