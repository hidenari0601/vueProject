<template>
  <div id="Input">
    <ul id="listErr">
      <li
        style="color:#FF0000"
        v-for="(e, index)  in errors"
        v-bind:key="index"
      >[ERR{{index}}] : {{e}}</li>
    </ul>
    <h1 style="color:	#00CED1">入力欄1</h1>
    <input v-model="text" placeholder="入力してね">
    <button @click="apply">apply</button>
    <button @click="listClear">listClear</button>
    <p>Message is: {{ text1 }}</p>
    <ul id="listText">
      <li v-for="(t, index)  in texts" v-bind:key="index">[{{index}}] : {{t}}</li>
    </ul>
    <h1 style="color:	#00CED1">掛け算</h1>
    <input input type="number" v-model="num1" placeholder="数値1">
    <input input type="number" v-model="num2" placeholder="数値2">
    <br>
    <button @click="calc">calc</button>
    <br>
    <p>計算結果: {{ result }}</p>
    <!-- <p style="color:#FF0000">{{ errors }}</p> -->
  </div>
</template>

<script>
export default {
  name: "Input",
  data() {
    return {
      text: "",
      text1: "",
      num1: 0,
      num2: 0,
      result: 0,
      errors: [],
      texts: []
    };
  },
  methods: {
    apply: function() {
      this.errors = [];
      this.text1 = this.text;
      if (this.texts.length === 5) {
        this.errors.push("5行までしか入力できません！");
        return;
      }
      this.texts.push(this.text);
    },
    listClear: function() {
      this.errors = [];
      this.texts = [];
    },
    calc: function() {
      this.errors = [];

      if (this.num1 === "") {
        this.errors.push("数値１が未入力です");
        return;
      }
      if (this.num2 === "") {
        this.errors.push("数値２が未入力です");
        return;
      }
      if (this.num1 === 0 || this.num2 === 0) {
        this.errors.push("0はいくら掛けても0じゃ！！！");
        return;
      }
      this.result = this.num1 * this.num2;
    }
  }
};
</script>