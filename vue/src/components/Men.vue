<template>
  <div>
    <p v-on:click="showtext(item)" :class="color === item.name ? 'red' : ''" v-for="item in aaa">
      {{item.name}}: {{item.age}}
      <span v-if="item.age > 16">大龄青年</span>
    </p>
    <div>
      <p v-for="item in bbb">
        水果：{{item.name}}}
        <br/>
        价格：{{item.Price}}
        <br/>
        <button @click="item.Price = item.Price + 1">+1</button>
        <br/>
        剩余：{{item.residue}}
      </p>
      <h2>水果总数： {{product}}</h2>
    </div>
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
        color: this.name,
        aaa: [
          {name: 'xiaoming', age: 13},
          {name: 'xiaohong', age: 13},
          {name: 'xiaofang', age: 13},
          {name: 'xiaobai', age: 18},
        ],
        bbb: [
          {"Price": 18, "residue": 30, "name": "芒果"},
          {"Price": 12, "residue": 29, "name": "荔枝"},
          {"Price": 32, "residue" : 12, "name": "西瓜"},
          {"Price": 10, "residue": 10, "name": "桃子"},
        ]
      }
    },

    computed: {
      product() {
        return this.bbb.reduce((sum, item) => {
          console.log(sum, item);
          return sum + parseFloat(item.residue);
        }, 0)
      }
    },

    methods: {
      risePrice(index) {
        console.log(index);
      },
      showtext(item) {
        this.color = item.name
        this.$emit('seyHello', item.name)
      }
    },


  }
</script>

<style>
  .red {
    color: red;
  }

</style>
