<template>
  <div id="counter">
    <span>{{ num }}</span>
    <br>
    <button @click="addOne">up</button>
    <button @click="substractOne">down</button>
    <br>
    <p v-if="num === 0">Press 'up' or 'down' button!!!!</p>
    <button @click="clear">clear</button>
  </div>
</template>

<script>
export default {
  name: "Counter",
  data() {
    return {
      num: 0
    };
  },
  methods: {
    addOne: function() {
      this.num = this.num + 1;
    },
    substractOne: function() {
      this.num = this.num - 1;
    },
    clear: function() {
      this.num = 0;
    }
  }
};
</script>