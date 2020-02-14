<template>
  <div>
    <Counter/>
    <Input/>
  </div>
</template>

<script>
import Counter from "./components/Counter";
import Input from "./components/Input";

export default {
  name: "App",
  components: {
    Counter,
    Input
  }
};
</script>

<style>
</style>
